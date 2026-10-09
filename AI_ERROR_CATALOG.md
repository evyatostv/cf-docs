# AI_ERROR_CATALOG

This is the exhaustive catalog of all possible errors in the ClinicFlow application, organized by domain.

## AUTH Errors (CF-1xxx)

### CF-1000: deriveWrapKeyFromPin: empty pin
- **Name / Short Description**: Failure triggered in `crypto.js` at line 327
- **Technical Trigger**: `throw new Error('deriveWrapKeyFromPin: empty pin');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 327.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1001: deriveWrapKeyFromPin: missing salt
- **Name / Short Description**: Failure triggered in `crypto.js` at line 329
- **Technical Trigger**: `if (!wrapSalt) throw new Error('deriveWrapKeyFromPin: missing salt');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 329.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1002: wrapMasterKeyWithPin: round-trip verification failed
- **Name / Short Description**: Failure triggered in `crypto.js` at line 367
- **Technical Trigger**: `throw new Error('wrapMasterKeyWithPin: round-trip verification failed');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 367.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1003: wrapMasterKeyWithPin: document-key round-trip verification failed
- **Name / Short Description**: Failure triggered in `crypto.js` at line 370
- **Technical Trigger**: `throw new Error('wrapMasterKeyWithPin: document-key round-trip verification failed');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 370.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1004: unwrapMasterKeyWithPin: not a v2/v3 wrap
- **Name / Short Description**: Failure triggered in `crypto.js` at line 382
- **Technical Trigger**: `throw new Error('unwrapMasterKeyWithPin: not a v2/v3 wrap');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 382.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1005: unwrapMasterKeyWithPin: v3 wrap requires device pepper
- **Name / Short Description**: Failure triggered in `crypto.js` at line 389
- **Technical Trigger**: `throw new Error('unwrapMasterKeyWithPin: v3 wrap requires device pepper');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `crypto.js` around line 389.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1006: wrapForKeychain: safeStorage encryption not available
- **Name / Short Description**: Failure triggered in `keychain.js` at line 161
- **Technical Trigger**: `throw new Error('wrapForKeychain: safeStorage encryption not available');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `keychain.js` around line 161.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1007: wrapForKeychain: round-trip verification failed
- **Name / Short Description**: Failure triggered in `keychain.js` at line 170
- **Technical Trigger**: `throw new Error('wrapForKeychain: round-trip verification failed');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `keychain.js` around line 170.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1008: unwrapFromKeychain: not a keychain envelope
- **Name / Short Description**: Failure triggered in `keychain.js` at line 181
- **Technical Trigger**: `throw new Error('unwrapFromKeychain: not a keychain envelope');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `keychain.js` around line 181.
  3. Verify encryption keys and user PIN/passwords are correct.

### CF-1009: unwrapFromKeychain: safeStorage not available
- **Name / Short Description**: Failure triggered in `keychain.js` at line 184
- **Technical Trigger**: `throw new Error('unwrapFromKeychain: safeStorage not available');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `keychain.js` around line 184.
  3. Verify encryption keys and user PIN/passwords are correct.

## DB Errors (CF-2xxx)

### CF-2000: אימות הגיבוי לאחר היצירה נכשל — הקובץ נמחק.
- **Name / Short Description**: Failure triggered in `backup.js` at line 389
- **Technical Trigger**: `throw new Error('אימות הגיבוי לאחר היצירה נכשל — הקובץ נמחק.');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 389.
  3. Verify SQLite database integrity and file permissions.

### CF-2001: פורמט גיבוי לא תקין — הקובץ ריק או קטן מדי
- **Name / Short Description**: Failure triggered in `backup.js` at line 448
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין — הקובץ ריק או קטן מדי');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 448.
  3. Verify SQLite database integrity and file permissions.

### CF-2002: פורמט גיבוי לא תקין — קובץ ZIP גולמי, נדרש קובץ .cfbk מוצפן
- **Name / Short Description**: Failure triggered in `backup.js` at line 451
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין — קובץ ZIP גולמי, נדרש קובץ .cfbk מוצפן');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 451.
  3. Verify SQLite database integrity and file permissions.

### CF-2003: פורמט גיבוי לא תקין
- **Name / Short Description**: Failure triggered in `backup.js` at line 454
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 454.
  3. Verify SQLite database integrity and file permissions.

### CF-2004: פורמט גיבוי לא תקין
- **Name / Short Description**: Failure triggered in `backup.js` at line 466
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 466.
  3. Verify SQLite database integrity and file permissions.

### CF-2005: פורמט גיבוי לא תקין
- **Name / Short Description**: Failure triggered in `backup.js` at line 469
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 469.
  3. Verify SQLite database integrity and file permissions.

### CF-2006: פורמט גיבוי לא תקין
- **Name / Short Description**: Failure triggered in `backup.js` at line 472
- **Technical Trigger**: `throw new Error('פורמט גיבוי לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 472.
  3. Verify SQLite database integrity and file permissions.

### CF-2007: סיסמת גיבוי שגויה או קובץ פגום
- **Name / Short Description**: Failure triggered in `backup.js` at line 493
- **Technical Trigger**: `throw new Error('סיסמת גיבוי שגויה או קובץ פגום');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 493.
  3. Verify SQLite database integrity and file permissions.

### CF-2008: סיסמת גיבוי שגויה או קובץ פגום
- **Name / Short Description**: Failure triggered in `backup.js` at line 510
- **Technical Trigger**: `throw new Error('סיסמת גיבוי שגויה או קובץ פגום');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `backup.js` around line 510.
  3. Verify SQLite database integrity and file permissions.

### CF-2009: auditLog create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 629
- **Technical Trigger**: `console.error('auditLog create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 629.
  3. Verify SQLite database integrity and file permissions.

### CF-2010: doctor_med_library create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 666
- **Technical Trigger**: `console.error('doctor_med_library create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 666.
  3. Verify SQLite database integrity and file permissions.

### CF-2011: patient_medications create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 711
- **Technical Trigger**: `console.error('patient_medications create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 711.
  3. Verify SQLite database integrity and file permissions.

### CF-2012: patient_imaging create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 734
- **Technical Trigger**: `console.error('patient_imaging create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 734.
  3. Verify SQLite database integrity and file permissions.

### CF-2013: patient_labs create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 759
- **Technical Trigger**: `console.error('patient_labs create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 759.
  3. Verify SQLite database integrity and file permissions.

### CF-2014: patient_goals create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 779
- **Technical Trigger**: `console.error('patient_goals create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 779.
  3. Verify SQLite database integrity and file permissions.

### CF-2015: waitlist create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 799
- **Technical Trigger**: `console.error('waitlist create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 799.
  3. Verify SQLite database integrity and file permissions.

### CF-2016: patient_problems create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 829
- **Technical Trigger**: `console.error('patient_problems create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 829.
  3. Verify SQLite database integrity and file permissions.

### CF-2017: session_packages create failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 849
- **Technical Trigger**: `console.error('session_packages create failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 849.
  3. Verify SQLite database integrity and file permissions.

### CF-2018: Opinions visitId rebuild failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 895
- **Technical Trigger**: `console.error('Opinions visitId rebuild failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 895.
  3. Verify SQLite database integrity and file permissions.

### CF-2019: Defensive column check failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 898
- **Technical Trigger**: `console.error('Defensive column check failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 898.
  3. Verify SQLite database integrity and file permissions.

### CF-2020: [db] visit→appointment backfill error (non-fatal):
- **Name / Short Description**: Failure triggered in `db.js` at line 1400
- **Technical Trigger**: `console.error('[db] visit→appointment backfill error (non-fatal):', err && err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1400.
  3. Verify SQLite database integrity and file permissions.

### CF-2021: [db] orphan repair error (non-fatal):
- **Name / Short Description**: Failure triggered in `db.js` at line 1408
- **Technical Trigger**: `console.error('[db] orphan repair error (non-fatal):', err && err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1408.
  3. Verify SQLite database integrity and file permissions.

### CF-2022: נדרש להתחבר למערכת
- **Name / Short Description**: Failure triggered in `db.js` at line 1441
- **Technical Trigger**: `throw new Error('נדרש להתחבר למערכת');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1441.
  3. Verify SQLite database integrity and file permissions.

### CF-2023: updateUser: refusing to update non-allowlisted column 
- **Name / Short Description**: Failure triggered in `db.js` at line 1497
- **Technical Trigger**: `throw new Error(`updateUser: refusing to update non-allowlisted column "${key}"`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1497.
  3. Verify SQLite database integrity and file permissions.

### CF-2024: [db] orphan repair ABORTED — could not write safety backup:
- **Name / Short Description**: Failure triggered in `db.js` at line 1683
- **Technical Trigger**: `console.error('[db] orphan repair ABORTED — could not write safety backup:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1683.
  3. Verify SQLite database integrity and file permissions.

### CF-2025: orphan repair incomplete: 
- **Name / Short Description**: Failure triggered in `db.js` at line 1693
- **Technical Trigger**: `throw new Error('orphan repair incomplete: ' + JSON.stringify(remaining));`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1693.
  3. Verify SQLite database integrity and file permissions.

### CF-2026: [db] orphan repair rolled back, DB left unchanged (backup retained):
- **Name / Short Description**: Failure triggered in `db.js` at line 1701
- **Technical Trigger**: `console.error('[db] orphan repair rolled back, DB left unchanged (backup retained):', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1701.
  3. Verify SQLite database integrity and file permissions.

### CF-2027: storeSetting failed (key=${key}):
- **Name / Short Description**: Failure triggered in `db.js` at line 1717
- **Technical Trigger**: `console.error(`storeSetting failed (key=${key}):`, e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 1717.
  3. Verify SQLite database integrity and file permissions.

### CF-2028: archivePatient failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 2385
- **Technical Trigger**: `console.error('archivePatient failed:', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 2385.
  3. Verify SQLite database integrity and file permissions.

### CF-2029: appendAuditLog: audit write FAILED (recordType=${entry.recordType}, seq=${seq}):
- **Name / Short Description**: Failure triggered in `db.js` at line 4096
- **Technical Trigger**: `console.error(`appendAuditLog: audit write FAILED (recordType=${entry.recordType}, seq=${seq}):`, e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4096.
  3. Verify SQLite database integrity and file permissions.

### CF-2030: חוות דעת מקורית לא נמצאה
- **Name / Short Description**: Failure triggered in `db.js` at line 4190
- **Technical Trigger**: `if (!original) throw new Error('חוות דעת מקורית לא נמצאה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4190.
  3. Verify SQLite database integrity and file permissions.

### CF-2031: [ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש מטופלים: 
- **Name / Short Description**: Failure triggered in `db.js` at line 4763
- **Technical Trigger**: `} catch (err) { throw new Error('[ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש מטופלים: ' + err.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4763.
  3. Verify SQLite database integrity and file permissions.

### CF-2032: [ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש ביקורים: 
- **Name / Short Description**: Failure triggered in `db.js` at line 4781
- **Technical Trigger**: `} catch (err) { throw new Error('[ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש ביקורים: ' + err.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4781.
  3. Verify SQLite database integrity and file permissions.

### CF-2033: [ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש חוות דעת: 
- **Name / Short Description**: Failure triggered in `db.js` at line 4791
- **Technical Trigger**: `} catch (err) { throw new Error('[ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש חוות דעת: ' + err.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4791.
  3. Verify SQLite database integrity and file permissions.

### CF-2034: [ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש מסמכים: 
- **Name / Short Description**: Failure triggered in `db.js` at line 4798
- **Technical Trigger**: `} catch (err) { throw new Error('[ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש מסמכים: ' + err.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4798.
  3. Verify SQLite database integrity and file permissions.

### CF-2035: [ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש תורים: 
- **Name / Short Description**: Failure triggered in `db.js` at line 4844
- **Technical Trigger**: `} catch (err) { throw new Error('[ERR-CF-4003] מסד הנתונים החזיר שגיאה בחיפוש תורים: ' + err.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4844.
  3. Verify SQLite database integrity and file permissions.

### CF-2036: סכום המסמך חייב להיות גדול מאפס
- **Name / Short Description**: Failure triggered in `db.js` at line 4972
- **Technical Trigger**: `throw new Error('סכום המסמך חייב להיות גדול מאפס');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4972.
  3. Verify SQLite database integrity and file permissions.

### CF-2037: תאריך המסמך אינו תקין
- **Name / Short Description**: Failure triggered in `db.js` at line 4974
- **Technical Trigger**: `if (!isRealIsoDate(input.date)) throw new Error('תאריך המסמך אינו תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4974.
  3. Verify SQLite database integrity and file permissions.

### CF-2038: סוג מסמך פיננסי לא נתמך
- **Name / Short Description**: Failure triggered in `db.js` at line 4981
- **Technical Trigger**: `if (!supportedTypes.includes(input.type)) throw new Error('סוג מסמך פיננסי לא נתמך');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 4981.
  3. Verify SQLite database integrity and file permissions.

### CF-2039: לא ניתן לבטל קבלת תשלום שכבר הונפקה
- **Name / Short Description**: Failure triggered in `db.js` at line 5073
- **Technical Trigger**: `throw new Error('לא ניתן לבטל קבלת תשלום שכבר הונפקה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5073.
  3. Verify SQLite database integrity and file permissions.

### CF-2040: לא ניתן לקשר את התשלום לחשבונית
- **Name / Short Description**: Failure triggered in `db.js` at line 5087
- **Technical Trigger**: `if (!invoice || !receipt) throw new Error('לא ניתן לקשר את התשלום לחשבונית');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5087.
  3. Verify SQLite database integrity and file permissions.

### CF-2041: החשבונית כבר קשורה לקבלה אחרת
- **Name / Short Description**: Failure triggered in `db.js` at line 5089
- **Technical Trigger**: `throw new Error('החשבונית כבר קשורה לקבלה אחרת');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5089.
  3. Verify SQLite database integrity and file permissions.

### CF-2042: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5487
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5487.
  3. Verify SQLite database integrity and file permissions.

### CF-2043: text is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5489
- **Technical Trigger**: `if (!text) throw new Error('text is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5489.
  3. Verify SQLite database integrity and file permissions.

### CF-2044: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5573
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5573.
  3. Verify SQLite database integrity and file permissions.

### CF-2045: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5667
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5667.
  3. Verify SQLite database integrity and file permissions.

### CF-2046: label is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5669
- **Technical Trigger**: `if (!label) throw new Error('label is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5669.
  3. Verify SQLite database integrity and file permissions.

### CF-2047: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5814
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5814.
  3. Verify SQLite database integrity and file permissions.

### CF-2048: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5986
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5986.
  3. Verify SQLite database integrity and file permissions.

### CF-2049: name is required
- **Name / Short Description**: Failure triggered in `db.js` at line 5988
- **Technical Trigger**: `if (!name) throw new Error('name is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 5988.
  3. Verify SQLite database integrity and file permissions.

### CF-2050: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 6290
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6290.
  3. Verify SQLite database integrity and file permissions.

### CF-2051: modality is required
- **Name / Short Description**: Failure triggered in `db.js` at line 6292
- **Technical Trigger**: `if (!modality) throw new Error('modality is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6292.
  3. Verify SQLite database integrity and file permissions.

### CF-2052: patientId is required
- **Name / Short Description**: Failure triggered in `db.js` at line 6379
- **Technical Trigger**: `if (!rec || !rec.patientId) throw new Error('patientId is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6379.
  3. Verify SQLite database integrity and file permissions.

### CF-2053: testName is required
- **Name / Short Description**: Failure triggered in `db.js` at line 6381
- **Technical Trigger**: `if (!testName) throw new Error('testName is required');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6381.
  3. Verify SQLite database integrity and file permissions.

### CF-2054: לא נמצא משתמש פעיל לשמירת הרשומה
- **Name / Short Description**: Failure triggered in `db.js` at line 6568
- **Technical Trigger**: `throw new Error('לא נמצא משתמש פעיל לשמירת הרשומה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6568.
  3. Verify SQLite database integrity and file permissions.

### CF-2055: getDataCounts: COUNT(${table}) failed:
- **Name / Short Description**: Failure triggered in `db.js` at line 6884
- **Technical Trigger**: `console.error(`getDataCounts: COUNT(${table}) failed:`, e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `db.js` around line 6884.
  3. Verify SQLite database integrity and file permissions.

### CF-2056: Secure deletion failed:
- **Name / Short Description**: Failure triggered in `secure-wipe.example.js` at line 34
- **Technical Trigger**: `console.error('Secure deletion failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.example.js` around line 34.
  3. Verify SQLite database integrity and file permissions.

### CF-2057: Batch deletion failed:
- **Name / Short Description**: Failure triggered in `secure-wipe.example.js` at line 82
- **Technical Trigger**: `console.error('Batch deletion failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.example.js` around line 82.
  3. Verify SQLite database integrity and file permissions.

### CF-2058: Sync deletion failed:
- **Name / Short Description**: Failure triggered in `secure-wipe.example.js` at line 176
- **Technical Trigger**: `console.error('Sync deletion failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.example.js` around line 176.
  3. Verify SQLite database integrity and file permissions.

### CF-2059: AUDIT: Deletion FAILED for patient ${patientId}
- **Name / Short Description**: Failure triggered in `secure-wipe.example.js` at line 211
- **Technical Trigger**: `console.error(`AUDIT: Deletion FAILED for patient ${patientId}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.example.js` around line 211.
  3. Verify SQLite database integrity and file permissions.

### CF-2060: AUDIT: Error: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.example.js` at line 212
- **Technical Trigger**: `console.error(`AUDIT: Error: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.example.js` around line 212.
  3. Verify SQLite database integrity and file permissions.

### CF-2061: Secure wipe failed:
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 65
- **Technical Trigger**: `*   console.error('Secure wipe failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 65.
  3. Verify SQLite database integrity and file permissions.

### CF-2062: filePath must be a non-empty string
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 79
- **Technical Trigger**: `throw new Error('filePath must be a non-empty string');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 79.
  3. Verify SQLite database integrity and file permissions.

### CF-2063: passes must be a positive integer (recommended: 3)
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 83
- **Technical Trigger**: `throw new Error('passes must be a positive integer (recommended: 3)');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 83.
  3. Verify SQLite database integrity and file permissions.

### CF-2064: pattern must be 
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 87
- **Technical Trigger**: `throw new Error('pattern must be "random" or "zeros"');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 87.
  3. Verify SQLite database integrity and file permissions.

### CF-2065: Path is not a regular file (directory, symlink, etc.)
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 102
- **Technical Trigger**: `throw new Error('Path is not a regular file (directory, symlink, etc.)');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 102.
  3. Verify SQLite database integrity and file permissions.

### CF-2066: Failed to access file: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 110
- **Technical Trigger**: `throw new Error(`Failed to access file: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 110.
  3. Verify SQLite database integrity and file permissions.

### CF-2067: Overwrite failed during pass ${passesCompleted + 1}: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 136
- **Technical Trigger**: `throw new Error(`Overwrite failed during pass ${passesCompleted + 1}: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 136.
  3. Verify SQLite database integrity and file permissions.

### CF-2068: Deletion failed: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 153
- **Technical Trigger**: `throw new Error(`Deletion failed: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 153.
  3. Verify SQLite database integrity and file permissions.

### CF-2069: Secure wipe failed:
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 181
- **Technical Trigger**: `*   console.error('Secure wipe failed:', err.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 181.
  3. Verify SQLite database integrity and file permissions.

### CF-2070: filePath must be a non-empty string
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 195
- **Technical Trigger**: `throw new Error('filePath must be a non-empty string');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 195.
  3. Verify SQLite database integrity and file permissions.

### CF-2071: passes must be a positive integer
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 199
- **Technical Trigger**: `throw new Error('passes must be a positive integer');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 199.
  3. Verify SQLite database integrity and file permissions.

### CF-2072: pattern must be 
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 203
- **Technical Trigger**: `throw new Error('pattern must be "random" or "zeros"');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 203.
  3. Verify SQLite database integrity and file permissions.

### CF-2073: Path is not a regular file
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 217
- **Technical Trigger**: `throw new Error('Path is not a regular file');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 217.
  3. Verify SQLite database integrity and file permissions.

### CF-2074: Failed to access file: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 220
- **Technical Trigger**: `throw new Error(`Failed to access file: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 220.
  3. Verify SQLite database integrity and file permissions.

### CF-2075: Overwrite failed during pass ${passesCompleted + 1}: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 246
- **Technical Trigger**: `throw new Error(`Overwrite failed during pass ${passesCompleted + 1}: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 246.
  3. Verify SQLite database integrity and file permissions.

### CF-2076: Deletion failed: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 262
- **Technical Trigger**: `throw new Error(`Deletion failed: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 262.
  3. Verify SQLite database integrity and file permissions.

### CF-2077: filePaths must be an array
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 300
- **Technical Trigger**: `throw new Error('filePaths must be an array');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 300.
  3. Verify SQLite database integrity and file permissions.

### CF-2078: Cannot stat file: ${err.message}
- **Name / Short Description**: Failure triggered in `secure-wipe.js` at line 358
- **Technical Trigger**: `throw new Error(`Cannot stat file: ${err.message}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `secure-wipe.js` around line 358.
  3. Verify SQLite database integrity and file permissions.

## NETWORK Errors (CF-3xxx)

### CF-3000: [supabaseLogin] signInWithPassword failed:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 78
- **Technical Trigger**: `console.error('[supabaseLogin] signInWithPassword failed:', JSON.stringify({`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 78.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3001: [supabaseLogin] threw (network/other):
- **Name / Short Description**: Failure triggered in `supabase.js` at line 171
- **Technical Trigger**: `console.error('[supabaseLogin] threw (network/other):', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 171.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3002: Get purchase info error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 204
- **Technical Trigger**: `console.error('Get purchase info error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 204.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3003: Check upgrade eligibility error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 237
- **Technical Trigger**: `console.error('Check upgrade eligibility error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 237.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3004: Logout error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 253
- **Technical Trigger**: `console.error('Logout error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 253.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3005: checkUserAccess Supabase error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 382
- **Technical Trigger**: `console.error('checkUserAccess Supabase error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 382.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3006: Check user access error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 452
- **Technical Trigger**: `console.error('Check user access error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 452.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3007: saveMachineFingerprint error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 514
- **Technical Trigger**: `console.error('saveMachineFingerprint error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 514.
  3. Verify Supabase connection, API keys, and network connectivity.

### CF-3008: saveMachineFingerprint error:
- **Name / Short Description**: Failure triggered in `supabase.js` at line 530
- **Technical Trigger**: `console.error('saveMachineFingerprint error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `supabase.js` around line 530.
  3. Verify Supabase connection, API keys, and network connectivity.

## UI Errors (CF-4xxx)

### CF-4000: [schema-guard] DB schema_version ${dbVersion} > app ${appVersion}. Refusing to migrate; opening read-only.
- **Name / Short Description**: Failure triggered in `index.js` at line 653
- **Technical Trigger**: `console.error(`[schema-guard] DB schema_version ${dbVersion} > app ${appVersion}. Refusing to migrate; opening read-only.`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 653.
  3. Verify IPC payload and UI component state.

### CF-4001: [schema-guard] pre-migration backup FAILED:
- **Name / Short Description**: Failure triggered in `index.js` at line 674
- **Technical Trigger**: `console.error('[schema-guard] pre-migration backup FAILED:', snapErr && snapErr.message ? snapErr.message : snapErr);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 674.
  3. Verify IPC payload and UI component state.

### CF-4002: [schema-guard] guard threw:
- **Name / Short Description**: Failure triggered in `index.js` at line 679
- **Technical Trigger**: `console.error('[schema-guard] guard threw:', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 679.
  3. Verify IPC payload and UI component state.

### CF-4003: [daily-backup] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 751
- **Technical Trigger**: `console.error('[daily-backup] failed:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 751.
  3. Verify IPC payload and UI component state.

### CF-4004: [daily-backup] check failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 839
- **Technical Trigger**: `console.error('[daily-backup] check failed:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 839.
  3. Verify IPC payload and UI component state.

### CF-4005: [patient-identity-migration] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1089
- **Technical Trigger**: `console.error('[patient-identity-migration] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1089.
  3. Verify IPC payload and UI component state.

### CF-4006: [appointment-migration] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1100
- **Technical Trigger**: `console.error('[appointment-migration] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1100.
  3. Verify IPC payload and UI component state.

### CF-4007: [document-migration] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1115
- **Technical Trigger**: `console.error('[document-migration] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1115.
  3. Verify IPC payload and UI component state.

### CF-4008: [finance-document-migration] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1123
- **Technical Trigger**: `console.error('[finance-document-migration] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1123.
  3. Verify IPC payload and UI component state.

### CF-4009: [medication-migration] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1135
- **Technical Trigger**: `console.error('[medication-migration] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1135.
  3. Verify IPC payload and UI component state.

### CF-4010: [dockey-rewrap] failed (non-fatal, retries next login):
- **Name / Short Description**: Failure triggered in `index.js` at line 1145
- **Technical Trigger**: `console.error('[dockey-rewrap] failed (non-fatal, retries next login):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1145.
  3. Verify IPC payload and UI component state.

### CF-4011: נדרש להתחבר למערכת
- **Name / Short Description**: Failure triggered in `index.js` at line 1182
- **Technical Trigger**: `throw new Error('נדרש להתחבר למערכת');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1182.
  3. Verify IPC payload and UI component state.

### CF-4012: נדרשת הרשאת מטפל
- **Name / Short Description**: Failure triggered in `index.js` at line 1234
- **Technical Trigger**: `throw new Error('נדרשת הרשאת מטפל');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1234.
  3. Verify IPC payload and UI component state.

### CF-4013: נדרשת הרשאת מטפל או עוזר
- **Name / Short Description**: Failure triggered in `index.js` at line 1241
- **Technical Trigger**: `throw new Error('נדרשת הרשאת מטפל או עוזר');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1241.
  3. Verify IPC payload and UI component state.

### CF-4014: verification mismatch
- **Name / Short Description**: Failure triggered in `index.js` at line 1500
- **Technical Trigger**: `if (!verifyBytes.equals(plainBytes)) throw new Error('verification mismatch');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 1500.
  3. Verify IPC payload and UI component state.

### CF-4015: מטופל לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 2708
- **Technical Trigger**: `throw new Error('מטופל לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2708.
  3. Verify IPC payload and UI component state.

### CF-4016: תבנית לא נמצאה
- **Name / Short Description**: Failure triggered in `index.js` at line 2748
- **Technical Trigger**: `throw new Error('תבנית לא נמצאה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2748.
  3. Verify IPC payload and UI component state.

### CF-4017: יצירת מסמך נכשלה — תוכן המסמך ריק או לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 2777
- **Technical Trigger**: `throw new Error('יצירת מסמך נכשלה — תוכן המסמך ריק או לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2777.
  3. Verify IPC payload and UI component state.

### CF-4018: יצירת PDF נכשלה — בדוק/י שהתבנית תקינה ושכל השדות מולאו
- **Name / Short Description**: Failure triggered in `index.js` at line 2818
- **Technical Trigger**: `throw new Error('יצירת PDF נכשלה — בדוק/י שהתבנית תקינה ושכל השדות מולאו');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2818.
  3. Verify IPC payload and UI component state.

### CF-4019: תבנית לא נמצאה
- **Name / Short Description**: Failure triggered in `index.js` at line 2841
- **Technical Trigger**: `throw new Error('תבנית לא נמצאה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2841.
  3. Verify IPC payload and UI component state.

### CF-4020: אישור המקור לתיקון לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 2851
- **Technical Trigger**: `throw new Error('אישור המקור לתיקון לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2851.
  3. Verify IPC payload and UI component state.

### CF-4021: מטופל לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 2971
- **Technical Trigger**: `throw new Error('מטופל לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 2971.
  3. Verify IPC payload and UI component state.

### CF-4022: RENDER_GONE:${details && details.reason ? details.reason : 
- **Name / Short Description**: Failure triggered in `index.js` at line 3136
- **Technical Trigger**: `onGone = (_e, details) => reject(new Error(`RENDER_GONE:${details && details.reason ? details.reason : 'unknown'}`));`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3136.
  3. Verify IPC payload and UI component state.

### CF-4023: [handleDbError] integrity_check details:
- **Name / Short Description**: Failure triggered in `index.js` at line 3755
- **Technical Trigger**: `console.error('[handleDbError] integrity_check details:', integ.messages?.join('; '));`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3755.
  3. Verify IPC payload and UI component state.

### CF-4024: [startup] SQLite integrity_check FAILED:
- **Name / Short Description**: Failure triggered in `index.js` at line 3842
- **Technical Trigger**: `console.error('[startup] SQLite integrity_check FAILED:', integrity.messages?.join('; '));`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3842.
  3. Verify IPC payload and UI component state.

### CF-4025: [startup] integrity check threw:
- **Name / Short Description**: Failure triggered in `index.js` at line 3851
- **Technical Trigger**: `console.error('[startup] integrity check threw:', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3851.
  3. Verify IPC payload and UI component state.

### CF-4026: [renderer:${p.context || 
- **Name / Short Description**: Failure triggered in `index.js` at line 3922
- **Technical Trigger**: `console.error(`[renderer:${p.context || 'error'}] ${p.message || ''}${p.where || ''}${p.stack ? '\n' + p.stack : ''}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3922.
  3. Verify IPC payload and UI component state.

### CF-4027: empty fingerprint
- **Name / Short Description**: Failure triggered in `index.js` at line 3996
- **Technical Trigger**: `if (!fp || !sid || !dfp) throw new Error('empty fingerprint');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 3996.
  3. Verify IPC payload and UI component state.

### CF-4028: token verify returned null
- **Name / Short Description**: Failure triggered in `index.js` at line 4002
- **Technical Trigger**: `if (!crypto.verifyActivationToken(tok, fp)) throw new Error('token verify returned null');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4002.
  3. Verify IPC payload and UI component state.

### CF-4029: master-key round-trip mismatch
- **Name / Short Description**: Failure triggered in `index.js` at line 4009
- **Technical Trigger**: `if (!un || !un.masterKey || !un.masterKey.equals(mk)) throw new Error('master-key round-trip mismatch');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4009.
  3. Verify IPC payload and UI component state.

### CF-4030: text round-trip mismatch
- **Name / Short Description**: Failure triggered in `index.js` at line 4013
- **Technical Trigger**: `if (crypto.decryptText(crypto.encryptText('selftest', mk), mk) !== 'selftest') throw new Error('text round-trip mismatch');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4013.
  3. Verify IPC payload and UI component state.

### CF-4031: [activation:login] unexpected error (resolving as network):
- **Name / Short Description**: Failure triggered in `index.js` at line 4266
- **Technical Trigger**: `console.error('[activation:login] unexpected error (resolving as network):', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4266.
  3. Verify IPC payload and UI component state.

### CF-4032: [activation:transferDevice] unexpected error (resolving as network):
- **Name / Short Description**: Failure triggered in `index.js` at line 4375
- **Technical Trigger**: `console.error('[activation:transferDevice] unexpected error (resolving as network):', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4375.
  3. Verify IPC payload and UI component state.

### CF-4033: [activation:checkDeviceStillBound] unexpected error:
- **Name / Short Description**: Failure triggered in `index.js` at line 4442
- **Technical Trigger**: `console.error('[activation:checkDeviceStillBound] unexpected error:', err && err.message ? err.message : err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4442.
  3. Verify IPC payload and UI component state.

### CF-4034: [getStableMachineId] write failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 4589
- **Technical Trigger**: `console.error('[getStableMachineId] write failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4589.
  3. Verify IPC payload and UI component state.

### CF-4035: [activation:setPin] master-key re-wrap failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 4762
- **Technical Trigger**: `console.error('[activation:setPin] master-key re-wrap failed:', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4762.
  3. Verify IPC payload and UI component state.

### CF-4036: [activation:setPin] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 4768
- **Technical Trigger**: `console.error('[activation:setPin] error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4768.
  3. Verify IPC payload and UI component state.

### CF-4037: [activation:verifyPin] brute-force fallback failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 4891
- **Technical Trigger**: `console.error('[activation:verifyPin] brute-force fallback failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4891.
  3. Verify IPC payload and UI component state.

### CF-4038: [activation:verifyPin] decrypt failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 4900
- **Technical Trigger**: `console.error('[activation:verifyPin] decrypt failed:', decryptErr.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4900.
  3. Verify IPC payload and UI component state.

### CF-4039: [activation:verifyPin] migrate failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 4928
- **Technical Trigger**: `} catch (e) { console.error('[activation:verifyPin] migrate failed:', e.message); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4928.
  3. Verify IPC payload and UI component state.

### CF-4040: [activation:verifyPin] unexpected error:
- **Name / Short Description**: Failure triggered in `index.js` at line 4934
- **Technical Trigger**: `console.error('[activation:verifyPin] unexpected error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4934.
  3. Verify IPC payload and UI component state.

### CF-4041: [activation:wipePin] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 4990
- **Technical Trigger**: `console.error('[activation:wipePin] error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 4990.
  3. Verify IPC payload and UI component state.

### CF-4042: Reset error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5004
- **Technical Trigger**: `console.error('Reset error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5004.
  3. Verify IPC payload and UI component state.

### CF-4043: Save master key error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5059
- **Technical Trigger**: `console.error('Save master key error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5059.
  3. Verify IPC payload and UI component state.

### CF-4044: [loginWithPin] v3 wrap requires device pepper but it is unavailable on this device/account
- **Name / Short Description**: Failure triggered in `index.js` at line 5095
- **Technical Trigger**: `console.error('[loginWithPin] v3 wrap requires device pepper but it is unavailable on this device/account');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5095.
  3. Verify IPC payload and UI component state.

### CF-4045: [loginWithPin] v2→v3 upgrade failed (non-fatal, stays v2):
- **Name / Short Description**: Failure triggered in `index.js` at line 5134
- **Technical Trigger**: `console.error('[loginWithPin] v2→v3 upgrade failed (non-fatal, stays v2):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5134.
  3. Verify IPC payload and UI component state.

### CF-4046: [loginWithPin] all
- **Name / Short Description**: Failure triggered in `index.js` at line 5162
- **Technical Trigger**: `console.error('[loginWithPin] all', candidates.length, 'candidate keys failed to decrypt masterkey');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5162.
  3. Verify IPC payload and UI component state.

### CF-4047: [loginWithPin] legacy machine-wrap → PIN upgrade failed (non-fatal, staying on machine-wrap):
- **Name / Short Description**: Failure triggered in `index.js` at line 5188
- **Technical Trigger**: `console.error('[loginWithPin] legacy machine-wrap → PIN upgrade failed (non-fatal, staying on machine-wrap):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5188.
  3. Verify IPC payload and UI component state.

### CF-4048: [loginWithPin] re-wrap failed (non-fatal):
- **Name / Short Description**: Failure triggered in `index.js` at line 5208
- **Technical Trigger**: `console.error('[loginWithPin] re-wrap failed (non-fatal):', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5208.
  3. Verify IPC payload and UI component state.

### CF-4049: [loginWithPin] PIN-wrap migration failed (non-fatal, stays on machine wrap):
- **Name / Short Description**: Failure triggered in `index.js` at line 5250
- **Technical Trigger**: `console.error('[loginWithPin] PIN-wrap migration failed (non-fatal, stays on machine wrap):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5250.
  3. Verify IPC payload and UI component state.

### CF-4050: PIN login error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5261
- **Technical Trigger**: `console.error('PIN login error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5261.
  3. Verify IPC payload and UI component state.

### CF-4051: [passkey:enable] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5323
- **Technical Trigger**: `console.error('[passkey:enable] error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5323.
  3. Verify IPC payload and UI component state.

### CF-4052: [passkey:authenticate] safeStorage decrypt failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 5370
- **Technical Trigger**: `console.error('[passkey:authenticate] safeStorage decrypt failed:', e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5370.
  3. Verify IPC payload and UI component state.

### CF-4053: [passkey:authenticate] v3 wrap requires device pepper but it is unavailable on this device/account
- **Name / Short Description**: Failure triggered in `index.js` at line 5403
- **Technical Trigger**: `console.error('[passkey:authenticate] v3 wrap requires device pepper but it is unavailable on this device/account');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5403.
  3. Verify IPC payload and UI component state.

### CF-4054: [passkey:authenticate] v2→v3 upgrade failed (non-fatal):
- **Name / Short Description**: Failure triggered in `index.js` at line 5422
- **Technical Trigger**: `} catch (e) { console.error('[passkey:authenticate] v2→v3 upgrade failed (non-fatal):', e && e.message ? e.message : e); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5422.
  3. Verify IPC payload and UI component state.

### CF-4055: [passkey:authenticate] all candidate keys failed to decrypt masterkey
- **Name / Short Description**: Failure triggered in `index.js` at line 5435
- **Technical Trigger**: `console.error('[passkey:authenticate] all candidate keys failed to decrypt masterkey');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5435.
  3. Verify IPC payload and UI component state.

### CF-4056: [passkey:authenticate] PIN-wrap migration failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 5443
- **Technical Trigger**: `} catch (e) { console.error('[passkey:authenticate] PIN-wrap migration failed:', e && e.message ? e.message : e); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5443.
  3. Verify IPC payload and UI component state.

### CF-4057: [passkey:authenticate] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5462
- **Technical Trigger**: `console.error('[passkey:authenticate] error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5462.
  3. Verify IPC payload and UI component state.

### CF-4058: [passkey:disable] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5476
- **Technical Trigger**: `console.error('[passkey:disable] error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5476.
  3. Verify IPC payload and UI component state.

### CF-4059: Keygen activation failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 5636
- **Technical Trigger**: `console.error('Keygen activation failed:', activation.errors);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5636.
  3. Verify IPC payload and UI component state.

### CF-4060: Keygen integration error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5641
- **Technical Trigger**: `console.error('Keygen integration error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5641.
  3. Verify IPC payload and UI component state.

### CF-4061: Supabase login error:
- **Name / Short Description**: Failure triggered in `index.js` at line 5665
- **Technical Trigger**: `console.error('Supabase login error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5665.
  3. Verify IPC payload and UI component state.

### CF-4062: [auth:login] master-key wrap upgrade failed (non-fatal, stays legacy):
- **Name / Short Description**: Failure triggered in `index.js` at line 5701
- **Technical Trigger**: `console.error('[auth:login] master-key wrap upgrade failed (non-fatal, stays legacy):', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5701.
  3. Verify IPC payload and UI component state.

### CF-4063: [pw-rehash] non-fatal:
- **Name / Short Description**: Failure triggered in `index.js` at line 5716
- **Technical Trigger**: `console.error('[pw-rehash] non-fatal:', e && e.message ? e.message : e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 5716.
  3. Verify IPC payload and UI component state.

### CF-4064: [seed] medication create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6225
- **Technical Trigger**: `console.error('[seed] medication create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6225.
  3. Verify IPC payload and UI component state.

### CF-4065: [seed] lab create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6247
- **Technical Trigger**: `console.error('[seed] lab create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6247.
  3. Verify IPC payload and UI component state.

### CF-4066: [seed] imaging create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6267
- **Technical Trigger**: `console.error('[seed] imaging create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6267.
  3. Verify IPC payload and UI component state.

### CF-4067: [seed] finance doc create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6302
- **Technical Trigger**: `console.error('[seed] finance doc create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6302.
  3. Verify IPC payload and UI component state.

### CF-4068: [seed] problems import failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6317
- **Technical Trigger**: `console.error('[seed] problems import failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6317.
  3. Verify IPC payload and UI component state.

### CF-4069: [seed] session package create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6333
- **Technical Trigger**: `console.error('[seed] session package create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6333.
  3. Verify IPC payload and UI component state.

### CF-4070: [seed] document create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6354
- **Technical Trigger**: `console.error('[seed] document create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6354.
  3. Verify IPC payload and UI component state.

### CF-4071: [seed] opinion create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6393
- **Technical Trigger**: `console.error('[seed] opinion create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6393.
  3. Verify IPC payload and UI component state.

### CF-4072: [seed] journal create failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 6412
- **Technical Trigger**: `console.error('[seed] journal create failed:', e && e.message);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6412.
  3. Verify IPC payload and UI component state.

### CF-4073: testing:seed error:
- **Name / Short Description**: Failure triggered in `index.js` at line 6439
- **Technical Trigger**: `console.error('testing:seed error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6439.
  3. Verify IPC payload and UI component state.

### CF-4074: [data:changeLocation] error:
- **Name / Short Description**: Failure triggered in `index.js` at line 6758
- **Technical Trigger**: `console.error('[data:changeLocation] error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 6758.
  3. Verify IPC payload and UI component state.

### CF-4075: [labels:list]
- **Name / Short Description**: Failure triggered in `index.js` at line 7088
- **Technical Trigger**: `catch (error) { console.error('[labels:list]', error && error.message); return []; }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7088.
  3. Verify IPC payload and UI component state.

### CF-4076: [visits:list] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 7430
- **Technical Trigger**: `console.error('[visits:list] failed:', error && error.message ? error.message : error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7430.
  3. Verify IPC payload and UI component state.

### CF-4077: [visits:listPage] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 7443
- **Technical Trigger**: `console.error('[visits:listPage] failed:', error && error.message ? error.message : error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7443.
  3. Verify IPC payload and UI component state.

### CF-4078: [visits:listPaged] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 7455
- **Technical Trigger**: `console.error('[visits:listPaged] failed:', error && error.message ? error.message : error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7455.
  3. Verify IPC payload and UI component state.

### CF-4079: הביקור סגור לעריכה
- **Name / Short Description**: Failure triggered in `index.js` at line 7503
- **Technical Trigger**: `throw new Error('הביקור סגור לעריכה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7503.
  3. Verify IPC payload and UI component state.

### CF-4080: יש להזין סיבת פתיחה מחדש
- **Name / Short Description**: Failure triggered in `index.js` at line 7988
- **Technical Trigger**: `throw new Error('יש להזין סיבת פתיחה מחדש');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 7988.
  3. Verify IPC payload and UI component state.

### CF-4081: יש להשלים שם עסק, כתובת, סטטוס ומספר עוסק/חברה בן 9 ספרות בהגדרות
- **Name / Short Description**: Failure triggered in `index.js` at line 8417
- **Technical Trigger**: `throw new Error('יש להשלים שם עסק, כתובת, סטטוס ומספר עוסק/חברה בן 9 ספרות בהגדרות');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 8417.
  3. Verify IPC payload and UI component state.

### CF-4082: עוסק פטור אינו רשאי לגבות מע״מ
- **Name / Short Description**: Failure triggered in `index.js` at line 8420
- **Technical Trigger**: `throw new Error('עוסק פטור אינו רשאי לגבות מע״מ');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 8420.
  3. Verify IPC payload and UI component state.

### CF-4083: למסמך מע״מ נדרש שיעור מע״מ תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 8423
- **Technical Trigger**: `throw new Error('למסמך מע״מ נדרש שיעור מע״מ תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 8423.
  3. Verify IPC payload and UI component state.

### CF-4084: טווח תאריכים לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 8796
- **Technical Trigger**: `throw new Error('טווח תאריכים לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 8796.
  3. Verify IPC payload and UI component state.

### CF-4085: לא נמצא מטפל להגדרות
- **Name / Short Description**: Failure triggered in `index.js` at line 10018
- **Technical Trigger**: `throw new Error('לא נמצא מטפל להגדרות');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10018.
  3. Verify IPC payload and UI component state.

### CF-4086: לא ניתן לערוך תבנית מערכת
- **Name / Short Description**: Failure triggered in `index.js` at line 10200
- **Technical Trigger**: `throw new Error('לא ניתן לערוך תבנית מערכת');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10200.
  3. Verify IPC payload and UI component state.

### CF-4087: יש לשכפל תבנית מערכת לפני הגדרת ברירת מחדל
- **Name / Short Description**: Failure triggered in `index.js` at line 10230
- **Technical Trigger**: `throw new Error('יש לשכפל תבנית מערכת לפני הגדרת ברירת מחדל');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10230.
  3. Verify IPC payload and UI component state.

### CF-4088: לא ניתן למחוק תבנית מערכת
- **Name / Short Description**: Failure triggered in `index.js` at line 10258
- **Technical Trigger**: `throw new Error('לא ניתן למחוק תבנית מערכת');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10258.
  3. Verify IPC payload and UI component state.

### CF-4089: importFromFile error:
- **Name / Short Description**: Failure triggered in `index.js` at line 10377
- **Technical Trigger**: `console.error('importFromFile error:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10377.
  3. Verify IPC payload and UI component state.

### CF-4090: מזהה ביקור לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 10392
- **Technical Trigger**: `throw new Error('מזהה ביקור לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10392.
  3. Verify IPC payload and UI component state.

### CF-4091: ביקור לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 10395
- **Technical Trigger**: `throw new Error('ביקור לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10395.
  3. Verify IPC payload and UI component state.

### CF-4092: נתיב קובץ לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 10401
- **Technical Trigger**: `throw new Error('נתיב קובץ לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10401.
  3. Verify IPC payload and UI component state.

### CF-4093: הקובץ לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 10410
- **Technical Trigger**: `throw new Error('הקובץ לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10410.
  3. Verify IPC payload and UI component state.

### CF-4094: נתיב קובץ לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 10413
- **Technical Trigger**: `throw new Error('נתיב קובץ לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10413.
  3. Verify IPC payload and UI component state.

### CF-4095: הקובץ גדול מ-50MB
- **Name / Short Description**: Failure triggered in `index.js` at line 10418
- **Technical Trigger**: `throw new Error('הקובץ גדול מ-50MB');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10418.
  3. Verify IPC payload and UI component state.

### CF-4096: סוג קובץ לא נתמך
- **Name / Short Description**: Failure triggered in `index.js` at line 10424
- **Technical Trigger**: `throw new Error('סוג קובץ לא נתמך');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10424.
  3. Verify IPC payload and UI component state.

### CF-4097: מזהה ביקור לא תקין
- **Name / Short Description**: Failure triggered in `index.js` at line 10430
- **Technical Trigger**: `throw new Error('מזהה ביקור לא תקין');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10430.
  3. Verify IPC payload and UI component state.

### CF-4098: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 10557
- **Technical Trigger**: `if (typeof storedPath !== 'string') throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10557.
  3. Verify IPC payload and UI component state.

### CF-4099: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 10561
- **Technical Trigger**: `throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10561.
  3. Verify IPC payload and UI component state.

### CF-4100: לא נבחר מטופל
- **Name / Short Description**: Failure triggered in `index.js` at line 10834
- **Technical Trigger**: `if (!payload || !payload.patientId) throw new Error('לא נבחר מטופל');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10834.
  3. Verify IPC payload and UI component state.

### CF-4101: מטופל לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 10836
- **Technical Trigger**: `if (!patient) throw new Error('מטופל לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10836.
  3. Verify IPC payload and UI component state.

### CF-4102: הקובץ אינו בתיבת הסריקה
- **Name / Short Description**: Failure triggered in `index.js` at line 10960
- **Technical Trigger**: `if (!setting.folderPath || (sourcePath !== inbox && !sourcePath.startsWith(inbox + path.sep))) throw new Error('הקובץ אינו בתיבת הסריקה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10960.
  3. Verify IPC payload and UI component state.

### CF-4103: מטופל לא נמצא
- **Name / Short Description**: Failure triggered in `index.js` at line 10973
- **Technical Trigger**: `if (!patient) throw new Error('מטופל לא נמצא');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10973.
  3. Verify IPC payload and UI component state.

### CF-4104: הקובץ אינו בתיבת הסריקה
- **Name / Short Description**: Failure triggered in `index.js` at line 10977
- **Technical Trigger**: `if (!setting.folderPath || (sourcePath !== inbox && !sourcePath.startsWith(inbox + path.sep))) throw new Error('הקובץ אינו בתיבת הסריקה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10977.
  3. Verify IPC payload and UI component state.

### CF-4105: הסריקה עדיין נכתבת. המתינו מספר שניות ורעננו.
- **Name / Short Description**: Failure triggered in `index.js` at line 10979
- **Technical Trigger**: `if (!queueEntry || !queueEntry.stable) throw new Error('הסריקה עדיין נכתבת. המתינו מספר שניות ורעננו.');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 10979.
  3. Verify IPC payload and UI component state.

### CF-4106: למסמך אין קובץ שמור
- **Name / Short Description**: Failure triggered in `index.js` at line 11007
- **Technical Trigger**: `if (!row?.filePath) throw new Error('למסמך אין קובץ שמור');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11007.
  3. Verify IPC payload and UI component state.

### CF-4107: נתיב מסמך בלתי מורשה
- **Name / Short Description**: Failure triggered in `index.js` at line 11010
- **Technical Trigger**: `if (sourcePath !== dataRoot && !sourcePath.startsWith(dataRoot + path.sep)) throw new Error('נתיב מסמך בלתי מורשה');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11010.
  3. Verify IPC payload and UI component state.

### CF-4108: קובץ המסמך חסר
- **Name / Short Description**: Failure triggered in `index.js` at line 11011
- **Technical Trigger**: `if (!fs.existsSync(sourcePath)) throw new Error('קובץ המסמך חסר');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11011.
  3. Verify IPC payload and UI component state.

### CF-4109: לא נבחרו מסמכים
- **Name / Short Description**: Failure triggered in `index.js` at line 11020
- **Technical Trigger**: `if (!requested.length) throw new Error('לא נבחרו מסמכים');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11020.
  3. Verify IPC payload and UI component state.

### CF-4110: המסמכים שנבחרו לא נמצאו
- **Name / Short Description**: Failure triggered in `index.js` at line 11024
- **Technical Trigger**: `if (!rows.length) throw new Error('המסמכים שנבחרו לא נמצאו');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11024.
  3. Verify IPC payload and UI component state.

### CF-4111: [documents:list] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 11078
- **Technical Trigger**: `console.error('[documents:list] failed:', error && error.message ? error.message : error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11078.
  3. Verify IPC payload and UI component state.

### CF-4112: [documents:listAll] failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 11091
- **Technical Trigger**: `console.error('[documents:listAll] failed:', error && error.message ? error.message : error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11091.
  3. Verify IPC payload and UI component state.

### CF-4113: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 11142
- **Technical Trigger**: `if (typeof storedPath !== 'string') throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11142.
  3. Verify IPC payload and UI component state.

### CF-4114: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 11146
- **Technical Trigger**: `throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11146.
  3. Verify IPC payload and UI component state.

### CF-4115: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 11296
- **Technical Trigger**: `if (typeof storedPath !== 'string') throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11296.
  3. Verify IPC payload and UI component state.

### CF-4116: Invalid path
- **Name / Short Description**: Failure triggered in `index.js` at line 11303
- **Technical Trigger**: `throw new Error('Invalid path');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11303.
  3. Verify IPC payload and UI component state.

### CF-4117: קובץ הגיבוי אינו מכיל מסד נתונים
- **Name / Short Description**: Failure triggered in `index.js` at line 11636
- **Technical Trigger**: `throw new Error('קובץ הגיבוי אינו מכיל מסד נתונים');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11636.
  3. Verify IPC payload and UI component state.

### CF-4118: הגיבוי פגום ואינו ניתן לשחזור (${valid.error}). הנתונים הקיימים לא שונו.
- **Name / Short Description**: Failure triggered in `index.js` at line 11646
- **Technical Trigger**: `throw new Error(`הגיבוי פגום ואינו ניתן לשחזור (${valid.error}). הנתונים הקיימים לא שונו.`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11646.
  3. Verify IPC payload and UI component state.

### CF-4119: לא ניתן ליצור גיבוי-ביניים לפני השחזור; השחזור בוטל והנתונים לא שונו.
- **Name / Short Description**: Failure triggered in `index.js` at line 11663
- **Technical Trigger**: `throw new Error('לא ניתן ליצור גיבוי-ביניים לפני השחזור; השחזור בוטל והנתונים לא שונו.');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11663.
  3. Verify IPC payload and UI component state.

### CF-4120: post-restore integrity_check failed
- **Name / Short Description**: Failure triggered in `index.js` at line 11687
- **Technical Trigger**: `if (!post.ok) throw new Error('post-restore integrity_check failed');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11687.
  3. Verify IPC payload and UI component state.

### CF-4121: [restore] CRITICAL: rollback failed:
- **Name / Short Description**: Failure triggered in `index.js` at line 11698
- **Technical Trigger**: `console.error('[restore] CRITICAL: rollback failed:', rbErr && rbErr.message ? rbErr.message : rbErr);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11698.
  3. Verify IPC payload and UI component state.

### CF-4122: השחזור נכשל; הנתונים הוחזרו למצב הקודם. (${swapErr.message || swapErr})
- **Name / Short Description**: Failure triggered in `index.js` at line 11700
- **Technical Trigger**: `throw new Error(`השחזור נכשל; הנתונים הוחזרו למצב הקודם. (${swapErr.message || swapErr})`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11700.
  3. Verify IPC payload and UI component state.

### CF-4123: הגיבוי פגום ואינו ניתן למיזוג (${srcValid.error}). הנתונים הקיימים לא שונו.
- **Name / Short Description**: Failure triggered in `index.js` at line 11768
- **Technical Trigger**: `throw new Error(`הגיבוי פגום ואינו ניתן למיזוג (${srcValid.error}). הנתונים הקיימים לא שונו.`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11768.
  3. Verify IPC payload and UI component state.

### CF-4124: מיזוג הגיבוי נכשל; לא בוצעו שינויים בנתונים. (${txErr.message || txErr})
- **Name / Short Description**: Failure triggered in `index.js` at line 11920
- **Technical Trigger**: `throw new Error(`מיזוג הגיבוי נכשל; לא בוצעו שינויים בנתונים. (${txErr.message || txErr})`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 11920.
  3. Verify IPC payload and UI component state.

### CF-4125: integrity_check: ${(integ.messages || []).join(
- **Name / Short Description**: Failure triggered in `index.js` at line 12125
- **Technical Trigger**: `throw new Error(`integrity_check: ${(integ.messages || []).join('; ')}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12125.
  3. Verify IPC payload and UI component state.

### CF-4126: foreign_key_check violations: ${JSON.stringify(fk.violations).slice(0, 300)}
- **Name / Short Description**: Failure triggered in `index.js` at line 12131
- **Technical Trigger**: `throw new Error(`foreign_key_check violations: ${JSON.stringify(fk.violations).slice(0, 300)}`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12131.
  3. Verify IPC payload and UI component state.

### CF-4127: currentUser.id חסר
- **Name / Short Description**: Failure triggered in `index.js` at line 12141
- **Technical Trigger**: `if (!currentUser?.id) throw new Error('currentUser.id חסר');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12141.
  3. Verify IPC payload and UI component state.

### CF-4128: לא ניתן ליצור שורת משתמש מקומית
- **Name / Short Description**: Failure triggered in `index.js` at line 12146
- **Technical Trigger**: `if (!after) throw new Error('לא ניתן ליצור שורת משתמש מקומית');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12146.
  3. Verify IPC payload and UI component state.

### CF-4129: masterKey חסר
- **Name / Short Description**: Failure triggered in `index.js` at line 12152
- **Technical Trigger**: `if (!masterKey) throw new Error('masterKey חסר');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12152.
  3. Verify IPC payload and UI component state.

### CF-4130: שחזור בדיקה נכשל
- **Name / Short Description**: Failure triggered in `index.js` at line 12278
- **Technical Trigger**: `throw new Error('שחזור בדיקה נכשל');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `index.js` around line 12278.
  3. Verify IPC payload and UI component state.

### CF-4131: [ClinicFlow] ${context}:
- **Name / Short Description**: Failure triggered in `app.js` at line 631
- **Technical Trigger**: `console.error(`[ClinicFlow] ${context}:`, err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 631.
  3. Verify IPC payload and UI component state.

### CF-4132: [ClinicFlow:${kind}] ${message}${where}
- **Name / Short Description**: Failure triggered in `app.js` at line 669
- **Technical Trigger**: `try { console.error(`[ClinicFlow:${kind}] ${message}${where}`, err); } catch (_) {}`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 669.
  3. Verify IPC payload and UI component state.

### CF-4133: User cancelled
- **Name / Short Description**: Failure triggered in `app.js` at line 1107
- **Technical Trigger**: `reject(new Error('User cancelled'));`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 1107.
  3. Verify IPC payload and UI component state.

### CF-4134: [ClinicFlow] blankShellGuard failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 5389
- **Technical Trigger**: `try { console.error('[ClinicFlow] blankShellGuard failed:', e); } catch (_) { /* never throw from the guard */ }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 5389.
  3. Verify IPC payload and UI component state.

### CF-4135: resetLocalSetup (handleLocalReset) failed
- **Name / Short Description**: Failure triggered in `app.js` at line 6022
- **Technical Trigger**: `console.error('resetLocalSetup (handleLocalReset) failed', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 6022.
  3. Verify IPC payload and UI component state.

### CF-4136: Passkey setup offer error:
- **Name / Short Description**: Failure triggered in `app.js` at line 6133
- **Technical Trigger**: `console.error('Passkey setup offer error:', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 6133.
  3. Verify IPC payload and UI component state.

### CF-4137: [handlePinLogin] activation status failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 6194
- **Technical Trigger**: `} catch (e) { console.error('[handlePinLogin] activation status failed:', e); }`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 6194.
  3. Verify IPC payload and UI component state.

### CF-4138: Activation error:
- **Name / Short Description**: Failure triggered in `app.js` at line 7032
- **Technical Trigger**: `console.error('Activation error:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 7032.
  3. Verify IPC payload and UI component state.

### CF-4139: [unlockApp] getActivationStatus failed
- **Name / Short Description**: Failure triggered in `app.js` at line 7487
- **Technical Trigger**: `console.error('[unlockApp] getActivationStatus failed', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 7487.
  3. Verify IPC payload and UI component state.

### CF-4140: [unlockApp] loginWithPin threw
- **Name / Short Description**: Failure triggered in `app.js` at line 7503
- **Technical Trigger**: `console.error('[unlockApp] loginWithPin threw', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 7503.
  3. Verify IPC payload and UI component state.

### CF-4141: Failed to load patient documents:
- **Name / Short Description**: Failure triggered in `app.js` at line 10803
- **Technical Trigger**: `console.error('Failed to load patient documents:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 10803.
  3. Verify IPC payload and UI component state.

### CF-4142: [ERR-CF-4002] saveVisit failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 11818
- **Technical Trigger**: `console.error('[ERR-CF-4002] saveVisit failed:', result.error || result);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 11818.
  3. Verify IPC payload and UI component state.

### CF-4143: deleteDocument failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 15284
- **Technical Trigger**: `console.error('deleteDocument failed:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 15284.
  3. Verify IPC payload and UI component state.

### CF-4144: reset failed
- **Name / Short Description**: Failure triggered in `app.js` at line 17918
- **Technical Trigger**: `console.error('reset failed', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 17918.
  3. Verify IPC payload and UI component state.

### CF-4145: [logout] failed (reloading anyway):
- **Name / Short Description**: Failure triggered in `app.js` at line 18127
- **Technical Trigger**: `console.error('[logout] failed (reloading anyway):', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 18127.
  3. Verify IPC payload and UI component state.

### CF-4146: CSV export failed
- **Name / Short Description**: Failure triggered in `app.js` at line 19043
- **Technical Trigger**: `console.error('CSV export failed', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 19043.
  3. Verify IPC payload and UI component state.

### CF-4147: template import failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 20493
- **Technical Trigger**: `console.error('template import failed:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 20493.
  3. Verify IPC payload and UI component state.

### CF-4148: [ERR-CF-4003] Global search failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 22942
- **Technical Trigger**: `console.error('[ERR-CF-4003] Global search failed:', res?.error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 22942.
  3. Verify IPC payload and UI component state.

### CF-4149: [ERR-CF-4003] Global search failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 23215
- **Technical Trigger**: `console.error('[ERR-CF-4003] Global search failed:', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23215.
  3. Verify IPC payload and UI component state.

### CF-4150: Lab CSV export failed
- **Name / Short Description**: Failure triggered in `app.js` at line 23354
- **Technical Trigger**: `console.error('Lab CSV export failed', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23354.
  3. Verify IPC payload and UI component state.

### CF-4151: bindEvents partial failure (some elements removed by redesign):
- **Name / Short Description**: Failure triggered in `app.js` at line 23850
- **Technical Trigger**: `console.error('bindEvents partial failure (some elements removed by redesign):', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23850.
  3. Verify IPC payload and UI component state.

### CF-4152: SpeechRecognition unavailable:
- **Name / Short Description**: Failure triggered in `app.js` at line 23878
- **Technical Trigger**: `console.error('SpeechRecognition unavailable:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23878.
  3. Verify IPC payload and UI component state.

### CF-4153: Speech recognition error:
- **Name / Short Description**: Failure triggered in `app.js` at line 23902
- **Technical Trigger**: `console.error('Speech recognition error:', e.error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23902.
  3. Verify IPC payload and UI component state.

### CF-4154: Failed to start recognition:
- **Name / Short Description**: Failure triggered in `app.js` at line 23924
- **Technical Trigger**: `console.error('Failed to start recognition:', err);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 23924.
  3. Verify IPC payload and UI component state.

### CF-4155: [ERR-CF-4003] Omnibar search failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 24533
- **Technical Trigger**: `console.error('[ERR-CF-4003] Omnibar search failed:', e);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 24533.
  3. Verify IPC payload and UI component state.

### CF-4156: טעינת רכיב נכשלה: ${src} (${response.status})
- **Name / Short Description**: Failure triggered in `app.js` at line 24654
- **Technical Trigger**: `throw new Error(`טעינת רכיב נכשלה: ${src} (${response.status})`);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 24654.
  3. Verify IPC payload and UI component state.

### CF-4157: [ERR-CF-4001] Component loading failed:
- **Name / Short Description**: Failure triggered in `app.js` at line 24661
- **Technical Trigger**: `console.error('[ERR-CF-4001] Component loading failed:', error);`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `app.js` around line 24661.
  3. Verify IPC payload and UI component state.

### CF-4158: iframe document unavailable
- **Name / Short Description**: Failure triggered in `calendar.js` at line 2053
- **Technical Trigger**: `if (!doc) throw new Error('iframe document unavailable');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `calendar.js` around line 2053.
  3. Verify IPC payload and UI component state.

### CF-4159: print unavailable
- **Name / Short Description**: Failure triggered in `calendar.js` at line 2059
- **Technical Trigger**: `if (!win || typeof win.print !== 'function') throw new Error('print unavailable');`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `calendar.js` around line 2059.
  3. Verify IPC payload and UI component state.

## GENERAL Errors (CF-5xxx)

### CF-5000: [logger] failed to write log entry:
- **Name / Short Description**: Failure triggered in `logger.js` at line 143
- **Technical Trigger**: `try { console.error('[logger] failed to write log entry:', _e && _e.message); } catch (_e2) {}`
- **Developer/AI Resolution Steps**:
  1. Check the inputs to the function throwing this error.
  2. Verify the state in `logger.js` around line 143.

