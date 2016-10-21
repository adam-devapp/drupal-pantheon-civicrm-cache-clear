# civicrm_cache_clear Drupal module

- Dynamically flush the CiviCRM cache when the pantheon disk path changes
-- This happens when Pantheon migrates servers, and the file system path changes with a new GUID
- Module caches the existing disk path value in Drupal cache (from DB), and will only update the value when environment variable has changed
-- This ensures minimal database requests are made
- Log to PHP error logs when clear cache action occurs