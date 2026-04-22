# Enable, Disable, or Delete Gmail and Google Drive Data

**Article ID:** GWS-06-01  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Manage the backup state of individual users' Gmail and Google Drive accounts. You can enable or disable backup at any time, and delete a user's backed-up data when it is no longer needed.

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- To delete data, the user must **not** have [Data Lock](https://help.druva.com/en/articles/8702846-data-lock-for-endpoints-microsoft-365-google-workspace) enabled.

---

## Enable Gmail backup for a user

Enabling backup activates the scheduled backup for the user's Gmail account.

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Gmail** tab.
3. Select the checkbox next to the user you want to enable.
4. Click **Enable**.
5. On the confirmation dialog, click **Yes**.

Repeat the same steps on the **Google Drive** tab to enable Drive backup independently.

---

## Disable Gmail or Google Drive backup for a user

Disabling backup stops new backups from running. Existing backed-up data is retained according to the retention policy.

1. Navigate to **Google Workspace > Gmail** (or **Google Drive**) tab.
2. Select the checkbox next to the user you want to disable.
3. Click **Disable**.
4. On the confirmation dialog, click **Yes**.

---

## Delete a user's Gmail or Google Drive data

Deleting removes the user's Cloud App account from inSync and schedules their backed-up data for permanent deletion after the rollback window expires.

> **⚠️ Important**  
> - You **cannot** delete a user's data if [Data Lock](https://help.druva.com/en/articles/8702846-data-lock-for-endpoints-microsoft-365-google-workspace) is enabled for that user.
> - Backed-up data **cannot be restored** after the user account is permanently deleted.
> - Deletion is temporary until the rollback window expires — use [Rollback Actions](GWS-06-04-rollback.md) to undo within the window.

1. Navigate to **Google Workspace > Gmail** (or **Google Drive**) tab.
2. Select the checkbox next to the user you want to delete.
3. Click the **three-dot menu (⋮)** and select **Delete**.
4. On the confirmation window, enter a **reason for deletion** (required; 10–150 characters). This reason is recorded in the **Admin Audit Trail**.
5. Click **Delete**.

The data is deleted temporarily. To undo the deletion, see [Rollback Deleted Devices and Snapshots](GWS-06-04-rollback.md).

### Rollback considerations

You **cannot** roll back a deletion if:

- The user's **Profile has been deleted**. Rollback the Profile first.
- The **user's Profile was changed** after deletion. Revert the Profile to the previous one.
- The **active license limit** for the user's account has been reached. Contact Druva Support to procure additional licenses.

---

## Delete snapshots

You can delete up to **20 snapshots at a time**. Snapshots belonging to users with Data Lock enabled cannot be deleted.

1. Navigate to **Google Workspace > Gmail** (or **Google Drive**) tab.
2. Click the username of the user whose snapshots you want to delete.
3. Click the **Backups** tab.
4. Select the snapshot(s) you want to delete.
5. Click **Delete Snapshot**.
6. Enter a **reason for deletion** (required; 10–150 characters).
7. Click **Delete**.

Snapshots are temporarily deleted. They can be rolled back within the configurable rollback window. After the window expires, deletion is permanent.

> **📝 Note**  
> Rollback Actions require the **Security Essentials** license. This feature is available for Druva Public Cloud customers only. Contact Support to obtain the license.

---

## Related articles

- [Manage and Delete Shared Drives](GWS-06-02-manage-shared-drives.md)
- [Delete Snapshots](GWS-06-03-delete-snapshots.md)
- [Rollback Deleted Devices and Snapshots](GWS-06-04-rollback.md)
- [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md)
- [Understand License Consumption](../05-monitor/GWS-05-04-license-consumption.md)
