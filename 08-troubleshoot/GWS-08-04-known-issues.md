# Known Issues and Limitations

**Article ID:** GWS-08-04  
**Audience:** All  
**Last reviewed:** April 2026

---

This page is the canonical reference for all known issues and platform limitations affecting Google Workspace backup, restore, and configuration in Druva inSync. Check this page before raising a support ticket — many of these are expected behaviors with documented workarounds.

---

## Backup limitations

| Issue | ID | Detail | Workaround |
|-------|----|--------|-----------|
| Large Google Slides or PPTX files fail during backup | INS-202881 | Files > 400 MB may time out during the Google API download phase and are skipped | Split into smaller files or convert to PDF before backing up — see [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md) |
| File names > 1,024 characters cannot be backed up | — | Google Drive files with very long names are skipped during backup | Rename the file with a shorter name |
| Google Forms and Google Sites are not backed up | — | These workloads are not supported by Druva | No workaround; these data types are excluded by design |
| My Computer folder is excluded | — | The local sync folder is not a cloud data source and is not protected | Back up these files using Druva Endpoint protection instead |
| Archived user data cannot be backed up | — | Google API limitation prevents access to archived accounts | No workaround |
| Google Vault data cannot be backed up | — | Google API limitation | No workaround |
| Birthday and Task calendars are not backed up | INS-182780 | Google API limitation | No workaround |
| Some Google Doc comments may be skipped | — | Google API availability affects comment backup | Known limitation; no workaround |
| My Computer files may appear in estimation API | — | The estimation API includes My Computer folder data in calculations, even though this data is not backed up | Treat estimation API results for My Computer data as informational only |

---

## Restore limitations

| Issue | ID | Detail | Workaround |
|-------|----|--------|-----------|
| Single deleted event not recreated in recurring series | INS-182239 | When a single event is deleted from a recurring Google Calendar series and an in-place restore is performed for the entire series, the deleted event is not recreated | Restore the individual event specifically rather than the entire series |
| Birthday calendar renamed to "Contacts" after restore | — | Google API limitation causes the birthday calendar to be renamed during restore | Manually rename the calendar after restore |
| Folder names > 255 characters cause restore failure | — | Google API returns `ErrorFolderSavePropertyError` for folder names exceeding 255 characters | Shorten the folder name before performing restore |
| In-place restore fails for files with multiple parent folders | — | If the selected parent folder is missing, in-place restore fails for files belonging to multiple parent folders | Restore the parent folder first, then restore the files |
| Themes and Images cannot be restored for Shared Drives | — | Internal API error prevents restore of Shared Drive themes and images | No workaround |
| Individual files from a deleted Shared Drive fail to restore | INS-175692 | If an entire Shared Drive is deleted and you try to restore individual files from an older snapshot, restore fails with `File not found` | Select the entire Shared Drive for restoration instead of individual files |
| Google native Drawings restore as JPEG | — | Druva restores Google Drawings as `.JPEG` image files rather than the native format | Download the original from a backup snapshot if the native format is required |
| Subfolders may not appear in Shared Drive restore UI | — | When a Shared Drive contains many folders, some subfolders may not appear in the folder tree in the UI. This is a display issue only — all items restore correctly | Proceed with the restore; all items are restored even if not visible in the tree |
| Gmail folder display language | — | If the Gmail display language is changed after a backup, folder names in the Druva Console continue to display in the language used at the time of backup, at both current and future restore points | This is cosmetic only; restore functionality is unaffected |

---

## Configuration limitations

| Issue | Detail | Workaround |
|-------|--------|-----------|
| Unlicensed Super Admin cannot discover Shared Drives | If Google Workspace is configured using an unlicensed Super Admin account, Shared Drives cannot be auto-discovered or manually added | Reconfigure Google Workspace using a licensed Super Admin account |
| UPN not supported in Verify Configuration step | During initial setup, the Verify Configuration field only accepts email addresses, not UPN | Enter the user's email address instead |
| Other Contacts restore not supported on GovCloud | Backup and restore of Other Contacts is unavailable on the GovCloud platform | No workaround for GovCloud deployments |
| Other Contacts restore to wrong location | In-place restore of Other Contacts goes to the "Others (inSync in-place Restore)" label rather than the actual Other Contacts section, due to a Google People API limitation | Check the label after restore |

---

## Data size discrepancies

Druva typically shows **more data** than Google Storage for the same content. This is expected behavior, not an error. Causes include:

- Druva counts native file sizes (Google Storage doesn't count native files).
- Druva retains deleted files until retention expires.
- Druva counts each copy of a file stored in multiple folders separately.

See [Why Does Druva Show More Data Than Google Storage?](../09-concepts/GWS-C-04-data-size-accounting.md) for full details.

---

## Related articles

- [Troubleshoot Google Workspace Backup Errors](GWS-08-01-troubleshoot-backup-errors.md)
- [Fix Google Workspace Connection Errors](GWS-08-03-fix-connection-errors.md)
- [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md)
- [Why Does Druva Show More Data Than Google Storage?](../09-concepts/GWS-C-04-data-size-accounting.md)
