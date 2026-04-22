# Set Up and Configure Shared Drives Backup

**Article ID:** GWS-02-04  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Google Shared Drives (also called Team Drives) store files owned by the team rather than individual users. Druva backs up Shared Drives separately from personal Google Drive accounts. Use this guide to configure auto-discovery, add drives, and define backup settings.

> **⚠️ Important**  
> Shared Drives backup is currently available in select AWS regions. Contact your Druva Sales representative or Support to confirm availability in your region.

---

## Before you begin

- You have completed [Connect Druva to Google Workspace](GWS-02-01-connect-druva-to-gws.md).
- Google Workspace is connected and shows status **Connected** on the Overview page.
- The Druva app is enabled for the Organizational Units (OUs) that contain your Shared Drives.
- Each Shared Drive has at least **one active member** or a Group with at least one active member.
- You configured Google Workspace using a **licensed** Super Administrator account. Unlicensed admins cannot auto-discover or manually add Shared Drives.
- The Shared Drive belongs to your Google Workspace organization's domain.

> **📝 Note — Existing customers**  
> If you previously set up Google Workspace before Shared Drives support was added, you must [reconfigure Google Workspace](GWS-02-03-reconfigure-gws.md) before Shared Drives can be discovered.

---

## What Druva backs up for Shared Drives

| Category | Data backed up |
|----------|---------------|
| **Drive identity** | Name of the Shared Drive |
| **Members** | User ID, name, access rights, account creation date, active period |
| **Settings** | Drive themes, images, and configuration |
| **Files** | Supported MIME types, file metadata, sharing settings (internal and external) |
| **Folders** | Folder metadata, contents, and activity details |
| **Trash** | Deleted items within the drive |

---

## Option A — Auto-configure Shared Drives (recommended)

Auto-configuration discovers all Shared Drives in your organization and applies a consistent backup policy to all of them. New drives added to Google Workspace are automatically discovered every 24 hours.

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Shared Drives** tab.
3. Click **Auto Configuration**.  
   The **Auto Configuration Settings** window appears.
4. Configure the settings:

| Field | Description |
|-------|-------------|
| **Auto discover Shared Drives for Backup** | When enabled, Druva discovers new Shared Drives every 24 hours. Enabled by default. |
| **Auto-assign storage** | When enabled, Druva automatically assigns storage to newly discovered drives. Storage must be assigned before a drive can be backed up. |
| **Assign Storage** | Select the storage region for new drives. Storage cannot be changed after assignment. |
| **Backup frequency** | How often Druva backs up each Shared Drive. |
| **Retain daily backups for** | Number of days to retain daily backup snapshots. Enter `0` for unlimited retention. |
| **Retain weekly backups for** | Number of weeks to retain weekly backups (last backup each Sunday). Enter `0` for unlimited. |
| **Retain monthly backups for** | Number of months to retain monthly backups (last backup of each month). Enter `0` for unlimited. |
| **File exclusions — Files** | File extensions to exclude from backup (comma-separated). |
| **File exclusions — Folders** | Absolute folder paths to exclude (comma-separated, e.g., `Sales/Reports/2015`). |

5. Click **Save**.

Druva begins discovering Shared Drives. Discovered drives appear in the Shared Drives list.

> **⚠️ Important**  
> Auto-configuration settings apply to **all subsequently discovered** Shared Drives. You can override settings for individual drives using custom configuration (Option B).

---

## Option B — Custom-configure individual Shared Drives

Use this option to apply different backup settings to specific drives.

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the name of the Shared Drive you want to configure.  
   The **Configure Shared Drives Backup** page appears.
3. Select **Custom** (instead of **Use Default**).
4. Configure the backup frequency, retention settings, and file exclusions as needed.
5. Click **Save**.

---

## Add a Shared Drive manually

If a drive is not being auto-discovered (for example, if auto-discovery is disabled, or you need to add a drive immediately), add it manually.

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the **three-dot menu (⋮)** in the top-right corner.
3. Click **Add Shared Drives**.
4. Enter the following details:

| Field | Description |
|-------|-------------|
| **Shared Drives Account URL** | The URL of the Shared Drive from your Google Drive account |
| **Assign storage** | Select a storage region. Cannot be changed after assignment. |
| **Backup & Retention** | Select **Use Default** to apply auto-configuration settings, or **Custom** to define settings for this drive only |

5. Click **Save**.

The new drive appears in the Shared Drives list.

---

## Discover Shared Drives on demand

If auto-discovery is enabled but you need Druva to discover new drives immediately (without waiting for the 24-hour cycle):

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the **three-dot menu (⋮)**.
3. Click **Discover Shared Drives**.

Druva runs discovery immediately. If Auto-assign storage is enabled, Druva assigns storage and backup settings automatically. If not, new drives appear with status **Not Configured**.

Also see [Force Sync of Google Shared Drives](../08-troubleshoot/GWS-08-02-force-sync-shared-drives.md).

---

## Enable Data Lock for a Shared Drive

Data Lock prevents deletion of snapshots and modification of retention settings. Only Cloud Administrators can enable it.

1. When adding or editing a Shared Drive, scroll to the **Data Lock** section.
2. Select **Enable Data Lock**.
3. Click **Yes** on the confirmation dialog.

> **🚨 Warning**  
> Once Data Lock is enabled, you **cannot**:
> - Delete snapshots
> - Edit the retention period
> - Disable Data Lock
> - Revert to default settings
> - Downgrade your inSync license

---

## Edit Shared Drive settings

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the Shared Drive name you want to edit.
3. On the **Summary** tab, click **Edit** in the **Shared Drive Settings** section.
4. Edit the required fields and click **Save**.

> **📝 Note**  
> You can only edit custom settings. Default (auto-configuration) settings must be changed via Auto Configuration.

---

## Related articles

- [Run an On-Demand Backup of Shared Drives](../03-backup/GWS-03-03-on-demand-backup-shared-drives.md)
- [Restore Shared Drives Data](../04-restore/GWS-04-03-restore-shared-drives.md)
- [Force Sync of Google Shared Drives](../08-troubleshoot/GWS-08-02-force-sync-shared-drives.md)
- [Manage and Delete Shared Drives](../06-manage/GWS-06-02-manage-shared-drives.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
