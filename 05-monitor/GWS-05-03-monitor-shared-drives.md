# Monitor Shared Drives Backup Status

**Article ID:** GWS-05-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

The Shared Drives tab in the Google Workspace dashboard lets you view backup status, data size, and configuration details for every Shared Drive in your organization.

---

## Access the Shared Drives tab

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Shared Drives** tab.

The header shows the total number of discovered Shared Drives.

---

## Understanding the Shared Drives list

| Column | Description |
|--------|-------------|
| **Name** | The name of the Shared Drive |
| **Last Completed Backup** | Date and time of the most recent successful backup. Click the column header to sort. |
| **Backup Data** | Total amount of data backed up for this Shared Drive |
| **App Status** | **Enabled**, **Disabled**, or **Not Configured** |
| **Last Backup Status** | Outcome of the most recent backup |
| **Status Details** | Error message if the backup failed |

---

## Filter Shared Drives

Click the **filter icon** to narrow the list:

| Filter | Options |
|--------|---------|
| **Last Backup Status** | Backed Up Successfully, Backed Up With Errors, Backup Failed, Never Backed Up |
| **App Status** | Enabled, Disabled, Not Configured |

---

## Actions from the Shared Drives list

| Action | How to access | What it does |
|--------|--------------|-------------|
| **Add Shared Drive** | Click **Add Shared Drive** | Manually add a drive by URL |
| **Discover Shared Drives** | Click three-dot menu (⋮) | Triggers immediate discovery without waiting for the 24-hour cycle |
| **Auto Configuration** | Click **Auto Configuration** | Edit discovery, storage, backup, and retention defaults |
| **Delete** | Select drive, click **Delete** | Removes the Shared Drive from inSync |

---

## Drill into a Shared Drive's details

Click a Shared Drive's **Name** to open its detail page. The detail page has three tabs:

### Summary tab

| Section | What it shows |
|---------|--------------|
| **Backup Summary** | Last completed backup date, last backup data size, last backup status, total backup data |
| **Storage Consumption** | Chart showing storage usage change over the last 90 days. Hover for daily values. |
| **Shared Drive Details** | Account name, account ID, status, date added |
| **Shared Drive Settings** | Current backup frequency, storage region, retention settings, file exclusions |

### Backups tab

Lists all available snapshots. Select a snapshot to restore or download from it.

- 🔒 **Padlock icon** — quarantined snapshot; cannot be restored or downloaded.
- ❗ **Exclamation icon** — latest clean snapshot; cannot be deleted.

### Activity Stream tab

Lists backup and restore activity logs for this Shared Drive:

- **Backup activities** — logs from the last 30 days (older logs auto-deleted when count exceeds 30 per month).
- **Download and Restore activities** — all activities, retained indefinitely.

Click **Download Logs** to export activity logs for a selected entry.

---

## Related articles

- [Navigate the Google Workspace Overview Dashboard](GWS-05-01-overview-dashboard.md)
- [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)
- [Run an On-Demand Backup of Shared Drives](../03-backup/GWS-03-03-on-demand-backup-shared-drives.md)
- [Force Sync of Google Shared Drives](../08-troubleshoot/GWS-08-02-force-sync-shared-drives.md)
- [Manage and Delete Shared Drives](../06-manage/GWS-06-02-manage-shared-drives.md)
