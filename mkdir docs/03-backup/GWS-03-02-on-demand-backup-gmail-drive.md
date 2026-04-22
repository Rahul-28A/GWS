# Run an On-Demand Backup of Gmail or Google Drive

**Article ID:** GWS-03-02  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

As a Druva Cloud Administrator, you can back up any user's Gmail or Google Drive data immediately — without waiting for the next scheduled backup. This is useful before a major change, after an incident, or to verify a new user's backup is working.

---

## Before you begin

- The user is assigned to a Profile with Google Workspace (SaaS Apps) enabled.
- The user's App Status is **Enabled** in the Google Workspace dashboard.
- At least one Google Workspace device is online.

---

## Back up Gmail data for a specific user

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Gmail** tab.
3. Select the checkbox next to the user whose data you want to back up.
4. Click **Backup Now**.

Druva initiates the backup immediately. To track progress:

- Go to **inSync Management Console > Jobs** page.
- Or check the [Backup and Restore tab](https://help.druva.com/en/articles/8829651-view-last-backup-details) in inSync Client.

---

## Back up Google Drive data for a specific user

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Google Drive** tab.
3. Select the checkbox next to the user whose data you want to back up.
4. Click **Backup Now**.

Druva initiates the backup immediately. To track progress:

- Go to **inSync Management Console > Jobs** page.
- Or check the [Backup and Restore tab](https://help.druva.com/en/articles/8829651-view-last-backup-details) in inSync Client.

---

## How emails with multiple attachments are stored

When Druva backs up a Gmail message that has multiple attachments, it creates:

- One `.eml` file for the email body.
- Separate `.eml` files for each attachment.

You can access these files through WebDAV. See [Access Legal Hold Data via WebDAV](../07-compliance/GWS-07-02-webdav-access.md) for details.

---

## Limitations

| Issue | Detail |
|-------|--------|
| Archived user data | Cannot be backed up — Google API limitation |
| Google Vault data | Cannot be backed up — Google API limitation |
| Files with names > 1,024 characters | Cannot be backed up — rename the file first |
| Google Slides / PPTX files > 400 MB | May fail during download — split or convert to PDF. See [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md) |

---

## Related articles

- [Schedule Google Workspace Backups](GWS-03-01-schedule-backups.md)
- [Run an On-Demand Backup of Shared Drives](GWS-03-03-on-demand-backup-shared-drives.md)
- [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
