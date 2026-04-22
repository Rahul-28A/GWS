# Manage and Delete Shared Drives

**Article ID:** GWS-06-02  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Manage the lifecycle of Shared Drives in Druva — enable, disable, or permanently delete a Shared Drive from your backup configuration. This article covers drive-level management; for snapshot-level management, see [Delete Snapshots](GWS-06-03-delete-snapshots.md).

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- To delete a Shared Drive, [Data Lock](https://help.druva.com/en/articles/8702846-data-lock-for-endpoints-microsoft-365-google-workspace) must **not** be enabled for that drive.

---

## Enable a Shared Drive

Enabling activates backup for a Shared Drive that was previously disabled or just discovered.

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the Shared Drive name you want to enable.
3. Click the **three-dot menu (⋮)** and select **Enable**.
4. On the confirmation dialog, click **Yes**.

---

## Disable a Shared Drive

Disabling stops new backups from running. Existing backed-up snapshots are retained per the retention policy.

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the Shared Drive name you want to disable.
3. Click the **three-dot menu (⋮)** and select **Disable**.
4. On the confirmation dialog, click **Yes**.

---

## Delete a Shared Drive

Deleting removes the Shared Drive from inSync and schedules its backed-up data for permanent deletion after the rollback window expires.

> **⚠️ Important**  
> - You **cannot** delete a Shared Drive if [Data Lock](https://help.druva.com/en/articles/8702846-data-lock-for-endpoints-microsoft-365-google-workspace) is enabled.
> - Data cannot be restored after permanent deletion.

1. Navigate to **Google Workspace > Shared Drives**.
2. Select the checkbox next to the Shared Drive you want to delete.
3. Click **Delete**.
4. Enter a **reason for deletion** (required; 10–150 characters). The reason is recorded in the **Admin Audit Trail**.
5. Click **Delete**.

The Shared Drive is temporarily deleted. To undo, see [Rollback Deleted Devices and Snapshots](GWS-06-04-rollback.md).

### Rollback considerations for Shared Drives

You **cannot** roll back a Shared Drive deletion if:

- You **deleted** the drive, then **re-discovered** (or re-added) the same drive while the first deletion is still in the rollback window, and then try to roll back the first deletion.
- You **deleted** the drive, then **deleted it again** from Rollback Actions — this makes the deletion permanent immediately.

> **📝 Note**  
> Rollback Actions require the **Security Essentials** license (Druva Public Cloud only). Contact Support to obtain this license.

---

## Monitor Shared Drive activity

To view backup and restore activity logs for a specific Shared Drive:

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the Shared Drive name.
3. Click the **Activity Stream** tab.

To download activity logs, select an activity entry and click **Download Logs**.

---

## View Shared Drive audit trails

To see all administrative actions taken on Shared Drives (deletions, configuration changes, etc.):

1. In the Druva Console, navigate to **Audit Trails > Admin Audit Trail**.
2. Under **Activities Type**, select **Google Shared Drives**.

---

## Related articles

- [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)
- [Delete Snapshots](GWS-06-03-delete-snapshots.md)
- [Rollback Deleted Devices and Snapshots](GWS-06-04-rollback.md)
- [Monitor Shared Drives Backup Status](../05-monitor/GWS-05-03-monitor-shared-drives.md)
- [Restore Shared Drives Data](../04-restore/GWS-04-03-restore-shared-drives.md)
