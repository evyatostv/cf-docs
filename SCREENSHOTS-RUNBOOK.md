# Screenshots Runbook — how the app screenshots in the docs were made

Internal note (not linked in the sidebar, not part of the public docs nav).
This explains **exactly** how the screenshots under `assets/screenshots/` were
captured and embedded, so they can be regenerated — e.g. before/at app publish.

> TL;DR: run the app's `dev-server.js` (renderer + mock API, no Electron/login),
> drive it with Playwright using a **seed/override init-script**, screenshot each
> screen, copy the PNGs into `assets/screenshots/`, and embed them in the guide
> pages with `![alt](../assets/screenshots/X.png ':size=820')`.

---

## What gets produced

14 PNGs in [assets/screenshots/](assets/screenshots/):

`login, home, patients, patient-profile, visit-editor, calendar, documents,`
`templates, finance, opinions, journal, medications, backup, settings`

Embedded across 13 pages (page → screenshot):

| Docs page | Screenshot(s) |
|---|---|
| `getting-started.md` | login |
| `app/installation.md` | login |
| `app/home.md` | home |
| `app/patients.md` | patients **+** patient-profile |
| `app/visit-editor.md` | visit-editor |
| `app/calendar.md` | calendar |
| `app/documents.md` | documents **+** templates |
| `app/finance.md` | finance |
| `app/opinions.md` | opinions |
| `app/journal.md` | journal |
| `app/medications.md` | medications |
| `app/settings.md` | settings |
| `app/backup-restore.md` | backup |

---

## Prerequisites & environment quirks (macOS, this machine)

- **Node / git aren't on the default PATH** in non-login shells. Prefix commands with:
  ```bash
  export PATH="/opt/homebrew/bin:/usr/local/bin:$PATH"
  ```
- **Playwright**: installed in a scratch dir (`/tmp/cf-shots`):
  ```bash
  cd /tmp && mkdir -p cf-shots && cd cf-shots && npm init -y && npm install playwright
  ```
- **Chromium version mismatch**: `playwright@latest` wanted a browser build that
  wasn't downloaded, but an older Chromium **headless-shell** was already cached.
  Instead of `npx playwright install`, point Playwright at the cached binary via
  `executablePath`. Find it with:
  ```bash
  find ~/Library/Caches/ms-playwright -maxdepth 4 -name "chrome-headless-shell"
  ```
  (At capture time it was `chromium_headless_shell-1223/...`. Update the path in
  `shoot.js` if the cache version differs — or just run `npx playwright install
  chromium` and drop the `executablePath` line.)

---

## Why a seed/override script is needed

The app ships a dev harness — [`ClinicFlow/dev-server.js`](../ClinicFlow/dev-server.js) —
that serves the real renderer (`ClinicFlow/src/renderer`) on `http://localhost:4000`
with `mock-api.js` (in-memory mock backend, all features unlocked, no
activation/PIN). Direct routes exist: `/home`, `/patients`, `/calendar`,
`/finance`, `/documents`, `/opinions`, `/journal`, `/settings`, `/backup`,
`/login`, etc. (see `/sitemap`).

**But `mock-api.js` is stale** relative to the redesigned renderer, so several
screens render empty or error until you override the API responses. Findings
(as of this capture — verify against current code, they may have been fixed):

- `homeGet` returned the wrong shape (no `ok`, wrong stat keys) → dashboard showed
  a "load failed" banner. Needs `{ ok, stats:{appointmentsToday,...}, recentVisits,
  recentDocuments, upcomingAppointments, charts:{visitsByWeek:[{period,total}]...} }`.
- `patientSearch` returned `{patients}` but the renderer reads `result.rows` → empty list.
- `getFinanceStats` returned `{totalRevenue}` but the screen needs `{ ok, stats:{monthly, outstanding, ...} }`.
- `listFinanceDocuments` returned `{documents,total}` but the screen wants a plain array.
- `listAllMedications` didn't exist → medications screen threw "load failed".
- Patient profile called `listPatientImaging` (and friends) that didn't exist → threw and reverted to the list.

The init-script below seeds `localStorage` (which the mock reads) **and**
intercepts `window.api` to (a) override the broken methods and (b) Proxy-stub any
**missing** method so nothing throws. It also sets `sys_onboarding_tour_seen` to
skip the first-run tour, and injects `[hidden]{display:none}` to hide menus whose
inline `display:flex` was overriding the `hidden` attribute.

---

## Files

Put both in `/tmp/cf-shots/`.

### `seed.js` — localStorage seed + `window.api` overrides (Playwright init-script)

```js
module.exports = `
(function(){
  function at(h,m){ const d=new Date(); d.setHours(h,m,0,0); return d.toISOString(); }
  const day = new Date().toISOString().split('T')[0];
  const S=(k,v)=>localStorage.setItem('cf_dev_'+k,JSON.stringify(v));
  const PATIENTS=[
    {id:'p1',fullName:'כהן דוד',nationalId:'123456789',phone:'050-1234567',email:'david@test.com',birthDate:'1980-01-15',gender:'male',status:'active',allergies:'פניצילין',backgroundDiseases:'יתר לחץ דם',pastSurgeries:'',continuousMeds:'',address:'תל אביב',notes:'',tags:'',createdAt:at(8,0),updatedAt:at(8,0)},
    {id:'p2',fullName:'לוי מיכל',nationalId:'987654321',phone:'052-9876543',email:'michal@test.com',birthDate:'1992-05-20',gender:'female',status:'active',allergies:'',backgroundDiseases:'סוכרת סוג 2',pastSurgeries:'',continuousMeds:'סימבסטטין',address:'חיפה',notes:'',tags:'',createdAt:at(8,1),updatedAt:at(8,1)},
    {id:'p3',fullName:'ישראלי יוסף',nationalId:'555555555',phone:'054-5555555',email:'yosef@test.com',birthDate:'1975-11-08',gender:'male',status:'active',allergies:'',backgroundDiseases:'',pastSurgeries:'ניתוח ברך 2020',continuousMeds:'',address:'ירושלים',notes:'מטופל קבוע',tags:'',createdAt:at(8,2),updatedAt:at(8,2)},
    {id:'p4',fullName:'אברהם שרה',nationalId:'111222333',phone:'053-1112222',email:'sarah@test.com',birthDate:'1988-03-12',gender:'female',status:'active',allergies:'אספירין',backgroundDiseases:'',pastSurgeries:'',continuousMeds:'',address:'באר שבע',notes:'',tags:'',createdAt:at(8,3),updatedAt:at(8,3)},
    {id:'p5',fullName:'בן-דוד עומר',nationalId:'444555666',phone:'050-4445556',email:'omer@test.com',birthDate:'2000-07-25',gender:'male',status:'active',allergies:'',backgroundDiseases:'',pastSurgeries:'',continuousMeds:'',address:'רמת גן',notes:'',tags:'',createdAt:at(8,4),updatedAt:at(8,4)}
  ];
  S('patients',PATIENTS);
  S('settings',{security:{autoLockMinutes:10,requirePasswordOnStart:true,requirePasswordForExport:true,blurOnBlur:true},branding:{name:'מרפאת פיתוח'},documents:{headerHtml:'',footerHtml:'',margins:{top:20,right:20,bottom:20,left:20}},sys_onboarding_tour_seen:'1',sys_activation_plan:'premium'});
  const appts=[
    {id:'a1',date:day,start:at(9,0),end:at(9,30),startAt:at(9,0),endAt:at(9,30),title:'כהן דוד',patientName:'כהן דוד',patientId:'p1',type:'ביקור',status:'scheduled',color:'blue',notes:''},
    {id:'a2',date:day,start:at(10,0),end:at(10,45),startAt:at(10,0),endAt:at(10,45),title:'לוי מיכל',patientName:'לוי מיכל',patientId:'p2',type:'מעקב',status:'arrived',color:'green',notes:''},
    {id:'a3',date:day,start:at(11,30),end:at(12,0),startAt:at(11,30),endAt:at(12,0),title:'ישראלי יוסף',patientName:'ישראלי יוסף',patientId:'p3',type:'ייעוץ',status:'scheduled',color:'blue',notes:''},
    {id:'a4',date:day,start:at(13,0),end:at(13,30),startAt:at(13,0),endAt:at(13,30),title:'אברהם שרה',patientName:'אברהם שרה',patientId:'p4',type:'בדיקה',status:'done',color:'orange',notes:''}
  ];
  S('appointments',appts);
  const docs=[
    {id:'d1',fileName:'סיכום ביקור — כהן דוד.pdf',type:'visit_summary',patientName:'כהן דוד',createdAt:at(9,35)},
    {id:'d2',fileName:'אישור רפואי — לוי מיכל.pdf',type:'medical_certificate',patientName:'לוי מיכל',createdAt:at(10,55)}
  ];
  S('documents',docs);
  S('finance',[
    {id:'f1',type:'invoice_receipt',docNumber:'1042',amount:450,patientName:'כהן דוד',paymentMethod:'אשראי',paid:true,createdAt:at(9,30)},
    {id:'f2',type:'receipt',docNumber:'1041',amount:300,patientName:'לוי מיכל',paymentMethod:'מזומן',paid:true,createdAt:at(10,50)},
    {id:'f3',type:'invoice',docNumber:'1040',amount:600,patientName:'ישראלי יוסף',paymentMethod:'העברה',paid:false,createdAt:at(12,10)}
  ]);
  S('journal',[
    {id:'j1',title:'סיכום ישיבת צוות',content:'לדון בנהלי קבלת מטופלים חדשים ובעדכון טפסי הסכמה.',tags:['מטלות מנהלתיות'],date:day,createdAt:at(8,0)},
    {id:'j2',title:'מעקב מחקר — סטטינים',content:'לבדוק מטופלים בטיפול ממושך לקראת הכינוס.',tags:['מחקר'],date:day,createdAt:at(8,15)}
  ]);
  S('opinions',[{id:'o1',title:'חוות דעת אורתופדית',patientName:'ישראלי יוסף',status:'signed',createdAt:at(12,30)}]);
  S('sticky',[{id:'s1',content:'להתקשר למעבדה לגבי תוצאות של שרה',color:'yellow',createdAt:at(8,30)}]);

  // Intercept window.api assignment to fix stale dev shapes + stub missing fns.
  let _api;
  Object.defineProperty(window,'api',{configurable:true,
    get(){return _api;},
    set(v){
      try{ patch(v); }catch(e){}
      _api = new Proxy(v, { get(t,p){
        const val = t[p];
        if (val !== undefined) return val;
        if (typeof p === 'symbol' || p === 'then' || p === 'toJSON') return undefined;
        return async () => ({ ok:true, items:[], rows:[], documents:[], entries:[], opinions:[], visits:[], total:0, counts:{active:0,archived:0,all:0} });
      }});
    }
  });
  document.addEventListener('DOMContentLoaded',()=>{ try{ const st=document.createElement('style'); st.textContent='[hidden]{display:none !important}'; document.head.appendChild(st); }catch(e){} });
  const meds=[
    {id:'m1',_patient:{id:'p2',fullName:'לוי מיכל'},name:'מטפורמין',dose:'850mg',frequency:'פעמיים ביום',startDate:day,status:'active'},
    {id:'m2',_patient:{id:'p2',fullName:'לוי מיכל'},name:'סימבסטטין',dose:'20mg',frequency:'פעם ביום (ערב)',startDate:day,status:'active'},
    {id:'m3',_patient:{id:'p3',fullName:'ישראלי יוסף'},name:'אומפרזול',dose:'20mg',frequency:'פעם ביום',startDate:day,status:'active'},
    {id:'m4',_patient:{id:'p1',fullName:'כהן דוד'},name:'אמוקסיצילין',dose:'500mg',frequency:'3 פעמים ביום',startDate:day,status:'ended'}
  ];
  const fin=[
    {id:'f1',type:'invoice_receipt',docNumber:'1042',amount:450,patientName:'כהן דוד',paymentMethod:'אשראי',paid:true,date:day,createdAt:at(9,30)},
    {id:'f2',type:'receipt',docNumber:'1041',amount:300,patientName:'לוי מיכל',paymentMethod:'מזומן',paid:true,date:day,createdAt:at(10,50)},
    {id:'f3',type:'invoice',docNumber:'1040',amount:600,patientName:'ישראלי יוסף',paymentMethod:'העברה',paid:false,date:day,createdAt:at(12,10)}
  ];
  function patch(api){
    api.patientSearch = async (payload) => {
      const f=(payload&&payload.filter)||'active';
      let rows = PATIENTS.filter(p => f==='all' ? true : f==='archived' ? p.status==='archived' : p.status==='active');
      return { ok:true, rows, total:rows.length, counts:{ active:PATIENTS.filter(p=>p.status==='active').length, archived:0, all:PATIENTS.length } };
    };
    api.getFinanceStats = async () => ({ ok:true, stats:{ monthly:1350, yearly:8600, outstanding:600, prevMonthly:1180, topPatient:'כהן דוד', topPatientAmount:450 } });
    api.listFinanceDocuments = async () => fin;
    api.listAllMedications = async () => ({ ok:true, items:meds });
    api.homeGet = async () => ({
      ok:true,
      stats:{ appointmentsToday:4, visitsToday:0, activePatients:5, newDocuments:2, workHours:6, monthlyGrowth:12, satisfactionRate:96, outstanding:600, balanceDue:600 },
      recentVisits:[
        {id:'v1',patientName:'כהן דוד',chiefComplaint:'כאב גרון',createdAt:at(9,25)},
        {id:'v2',patientName:'לוי מיכל',chiefComplaint:'מעקב סוכרת',createdAt:at(10,40)}
      ],
      recentDocuments:docs,
      upcomingAppointments:appts,
      charts:{ visitsByWeek:[{period:'2026-21',total:8},{period:'2026-22',total:11},{period:'2026-23',total:9},{period:'2026-24',total:13},{period:'2026-25',total:10}], visitsByMonth:[{period:'2026-02',total:32},{period:'2026-03',total:41},{period:'2026-04',total:38},{period:'2026-05',total:45},{period:'2026-06',total:22}], visitsByYear:[{period:'2024',total:380},{period:'2025',total:512},{period:'2026',total:178}] }
    });
  }
})();
`;
```

### `shoot.js` — navigate + screenshot every screen

```js
const { chromium } = require('playwright');
const seed = require('./seed.js');
const fs = require('fs');
// UPDATE if the cached chromium version differs (see Prerequisites):
const EXE='/Users/evyatardruyan/Library/Caches/ms-playwright/chromium_headless_shell-1223/chrome-headless-shell-mac-arm64/chrome-headless-shell';
const BASE='http://localhost:4000';
const OUT='/tmp/cf-shots/out'; fs.mkdirSync(OUT,{recursive:true});
const shot=(page,name,full=true)=>page.screenshot({path:OUT+'/'+name+'.png',fullPage:full});
const W=1440,H=950;
(async () => {
  const browser = await chromium.launch({ headless:true, executablePath:EXE });
  const ctx = await browser.newContext({ viewport:{width:W,height:H}, deviceScaleFactor:2 });
  await ctx.addInitScript(seed);
  const page = await ctx.newPage();

  await page.goto(BASE+'/login',{waitUntil:'load'}); await page.waitForTimeout(1500);
  await shot(page,'login',false);

  await page.goto(BASE+'/home',{waitUntil:'load'});
  await page.waitForSelector('[data-screen="home"]',{timeout:15000});
  await page.waitForTimeout(1800);
  await shot(page,'home');

  const screens=[['patients','patients'],['finance','finance'],['documents','documents'],
    ['templates','templates'],['opinions','opinions'],['medications','medications'],
    ['journal','journal'],['backup','backup'],['settings','settings']];
  for(const [scr,name] of screens){
    await page.click('[data-screen="'+scr+'"]'); await page.waitForTimeout(1600);
    await shot(page,name); console.log('shot',name);
  }

  // Calendar (month view shows today's events) — viewport clip, the 24h grid is tall
  await page.click('[data-screen="calendar"]'); await page.waitForTimeout(1600);
  await shot(page,'calendar',false); console.log('shot calendar');

  // Patient profile — DOUBLE-click a row (single click only selects)
  await page.click('[data-screen="patients"]'); await page.waitForTimeout(1500);
  const row = page.locator('#patient-table tr[data-id]').first();
  if(await row.count()){
    await row.dblclick().catch(()=>{}); await page.waitForTimeout(2000);
    await shot(page,'patient-profile'); console.log('shot patient-profile');
    const nv = page.locator('button:has-text("ביקור חדש")').first();
    if(await nv.count()){ await nv.click().catch(()=>{}); await page.waitForTimeout(1800); await shot(page,'visit-editor'); console.log('shot visit-editor'); }
  }
  await browser.close();
})();
```

---

## Run it

```bash
export PATH="/opt/homebrew/bin:/usr/local/bin:$PATH"

# 1) Start the dev server (renderer + mock API) — leave running
cd "/Users/evyatardruyan/all of clinic flow/ClinicFlow"
node dev-server.js          # serves http://localhost:4000

# 2) In another shell: capture
cd /tmp/cf-shots
node shoot.js               # writes /tmp/cf-shots/out/*.png

# 3) Copy into this docs repo
cp /tmp/cf-shots/out/*.png "/Users/evyatardruyan/all of clinic flow/docs.clinic-flow.co.il/assets/screenshots/"
```

---

## Embedding in markdown (Docsify)

- **Path is relative to the page's directory** (Docsify default, `relativePath`
  not enabled). So:
  - root pages (e.g. `getting-started.md`): `assets/screenshots/login.png`
  - `app/*.md` pages: `../assets/screenshots/X.png`
- Constrain display width with Docsify's size syntax (content max-width is 780px):
  ```markdown
  ![alt text](../assets/screenshots/home.png ':size=820')
  *Italic caption line.*
  ```

---

## Verify before committing

Serve the docs and confirm every embedded image returns 200 and renders:

```bash
cd "/Users/evyatardruyan/all of clinic flow/docs.clinic-flow.co.il"
python3 -m http.server 5055     # then open http://localhost:5055
```

(During this capture a Playwright script visited every page and asserted each
`.markdown-section img` had `naturalWidth > 0`. Re-use that if you want an
automated check.)

Then commit & push (`git`/`git-lfs` need the PATH export above; the docs repo is
**not** LFS, but `git-lfs` hooks exist elsewhere):

```bash
git add assets/screenshots app getting-started.md && git commit && git push origin main
```

The docs site (docs.clinic-flow.co.il) auto-deploys from `main` via Vercel.

---

## Gotchas learned

- **Single click only selects a patient row; double-click opens the profile.**
- **Patient rows are `#patient-table tr[data-id]`** (not `.patient-row`).
- **Appointments need `startAt`/`endAt`** (ISO) for the calendar grid; `start`/`end`
  are used by the list view, `date` (YYYY-MM-DD) for filtering/home.
- **Calendar deep-link (`/calendar`) doesn't fire the loader** — navigate by
  clicking the sidebar `[data-screen="calendar"]`. Same for finance/journal/meds.
  The default landing is month view, which nicely shows today's appointments.
- **Medications row reads `m._patient.fullName` and `m.dose`** (not `patientName`/`dosage`).
- The `[hidden]{display:none}` inject fixes action menus that render open because
  an inline `display:flex` overrides the `hidden` attribute.
- Full-page 2× PNGs are ~180–470 KB each (~3.2 MB total) — fine to commit.

---

## When redoing for the PUBLISHED app

The above captures the **dev renderer with mock + seeded data**. Options at publish:

1. **Easiest — keep using `dev-server.js`** (recommended for docs): re-run the
   scripts. First **re-check the stale-mock overrides** in `seed.js` against the
   shipped renderer — if `mock-api.js` was updated, you may be able to delete some
   overrides; if new screens/fields were added, add seed data/fields. Swap the
   sample Hebrew data for whatever you want shown.

2. **Real packaged Electron app** (true-to-ship chrome, real activation): drive it
   with Playwright's Electron support (`const { _electron } = require('playwright')`,
   `_electron.launch({ args:['.'] })` from the `ClinicFlow` dir, or against the
   built app). You'll need a real/activated account + real or imported data, and
   you'll click through actual login/PIN. Heavier, but no mock overrides needed.
   Use a throwaway clinic profile — never publish real patient data.

3. **Manual**: just run the app, set up demo data, and screenshot by hand.

Whichever route: keep the **same output filenames** so the existing
`![...](../assets/screenshots/X.png)` references in the guide pages keep working —
then it's a drop-in `cp` + commit.
