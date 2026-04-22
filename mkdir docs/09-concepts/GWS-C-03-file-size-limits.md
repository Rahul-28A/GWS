# File Size Limits and Workarounds

**Article ID:** GWS-C-03  
**Audience:** All  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva can back up most files without size restrictions, but certain file types and sizes hit Google API or infrastructure limits that cause them to be skipped during backup. This page lists every known limit and the recommended workaround for each.

---

## Google Slides and PowerPoint (.PPTX) files over 400 MB

**What happens:** Large Google Slides presentations or PowerPoint (`.PPTX`) files stored in Google Drive may fail to download during the Druva backup process. Google's infrastructure times out when serving very large presentation files via the export API, causing Druva to skip the file.

**Affected versions:** This is a known Google infrastructure limitation (tracked as INS-202881).

**Workarounds:**
- **Split the file** — divide the presentation into multiple smaller files, each under 400 MB.
- **Convert to PDF** — export the presentation as a PDF before backing up. PDFs of the same content are typically much smaller and back up reliably.

---

## File names longer than 1,024 characters

**What happens:** Google Drive files with names longer than 1,024 characters cannot be backed up. Druva skips these files without failing the entire backup job.

**Workaround:** Rename the affected file(s) to use a shorter name before the next backup run.

---

## Google account storage quota exhausted

**What happens:** Google Calendar attachments are stored in the user's Google Drive. If a user's Google account storage quota is full:
- Subsequent Gmail backups fail (because calendar event attachment links cannot be accessed).
- In-place restores also fail for the same user.

**Workarounds:**
- Ask the user to delete unnecessary files from their Google Drive to free up quota.
- Purchase additional Google Workspace storage for the user from Google.
- Re-run the backup after quota is freed — see [Run an On-Demand Backup](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md).

---

## Shared Drive files with known Google API limitations

Certain files in Shared Drives may not back up due to Google API restrictions documented by Google. For the full list of affected file types, see [Google's known issues with Shared Drives](https://support.google.com/a/answer/7337638).

---

## Related articles

- [Supported MIME Types for Google Workspace Backup](GWS-C-02-mime-types.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
- [Run an On-Demand Backup of Gmail or Google Drive](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md)
