# Monitor Gmail and Google Drive Backup Status

**Article ID:** GWS-05-02  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

The Gmail and Google Drive tabs in the Google Workspace dashboard show per-user backup status, data size, and error details. Use this view to identify failed backups, investigate errors, and take corrective actions.

---

## Access the Gmail or Google Drive tab

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Gmail** tab or the **Google Drive** tab.

---

## Understanding the user list

Each row represents one user. The columns show:

| Column | Description |
|--------|-------------|
| **User Name** | The user's display name |
| **Last Completed Backup** | Date and time of the most recent successful backup. Click the column header to sort by timestamp. |
| **Backup Data** | Total amount of data Druva has backed up for this user. Click the column header to sort by size. |
| **App Status** | Whether backup is **Enabled** or **Disabled** for this user. Icons indicate Legal Hold (⚖️) or persona backup configuration. |
| **Last Backup Status** | The outcome of the most recent backup run. |
| **Status Details** | If a backup failed, shows the error message. Click the error for more details. See [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md). |

---

## Filter users by backup status or app status

Click the **filter icon** to narrow the user list:

| Filter | Options |
|--------|---------|
| **Last Backup Status** | Backed Up Successfully, Backed Up With Errors, Backup Failed, Never Backed Up, Backup Throttled |
| **App Status** | Enabled, Disabled |

---

## Actions you can take from this view

Select one or more users using the checkbox, then choose an action:

| Action | What it does |
|--------|-------------|
| **Backup Now** | Starts an immediate on-demand backup for the selected user(s) |
| **Enable** | Enables backup for selected user(s) |
| **Disable** | Disables backup for selected user(s). Existing backup data is retained. |
| **Delete** | Removes the user's Cloud App account from inSync. **Backed-up data cannot be restored after deletion.** |

---

## View user details

Click a user's name to open the **User Details** page. From here you can:

- View backup history and individual snapshots on the **Backups** tab.
- Initiate a restore from the **Restore** button.
- Review per-snapshot backup data size and status.
- Check the **Activity Stream** tab for a log of backup and restore events.

---

## What backup statuses mean

| Status | Meaning | Recommended action |
|--------|---------|-------------------|
| **Backed Up Successfully** | Most recent backup completed with no errors | No action needed |
| **Backed Up With Errors** | Backup completed but some items were skipped | Click Status Details to identify which items failed |
| **Backup Failed** | Backup did not complete | See [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md) |
| **Never Backed Up** | No backup has ever run for this user | Verify the user is assigned to a Profile with SaaS Apps enabled and run Backup Now |
| **Backup Throttled** | Google API rate-limited the backup | Usually self-resolving on the next scheduled backup. If persistent, contact support. |

---

## Related articles

- [Navigate the Google Workspace Overview Dashboard](GWS-05-01-overview-dashboard.md)
- [Monitor Shared Drives Backup Status](GWS-05-03-monitor-shared-drives.md)
- [Run an On-Demand Backup of Gmail or Google Drive](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
- [Enable, Disable, or Delete Gmail and Google Drive Data](../06-manage/GWS-06-01-enable-disable-delete-gmail-drive.md)
