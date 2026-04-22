# Delete Snapshots (Gmail, Google Drive, Shared Drives)

**Article ID:** GWS-06-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Delete specific backup snapshots when they are no longer needed — for example, to free up storage or remove data per a legal hold release. You can delete up to **20 snapshots at a time**. Deleted snapshots can be recovered within the rollback window.

> **⚠️ Important**  
> Snapshots belonging to users or Shared Drives with [Data Lock](https://help.druva.com/en/articles/8702846-data-lock-for-endpoints-microsoft-365-google-workspace) enabled **cannot** be deleted.

---

## Delete Gmail snapshots

1. Navigate to **Google Workspace > Gmail**.
2. Click the **username** of the user whose snapshots you want to delete.
3. Click the **Backups** tab.
4. Select the snapshot(s) you want to delete (up to 20).
5. Click **Delete Snapshot**.
6. Enter a **reason for deletion** (required; 10–150 characters). Recorded in the Admin Audit Trail.
7. Click **Delete**.

---

## Delete Google Drive snapshots

1. Navigate to **Google Workspace > Google Drive**.
2. Click the **username** of the user whose snapshots you want to delete.
3. Click the **Backups** tab.
4. Select the snapshot(s) you want to delete (up to 20).
5. Click **Delete Snapshot**.
6. Enter a **reason for deletion** (required; 10–150 characters).
7. Click **Delete**.

---

## Delete Shared Drives snapshots

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the **Shared Drive name** whose snapshots you want to delete.
3. Click the **Backups** tab.
4. Select the snapshot(s) you want to delete (up to 20).
5. Click **Delete Snapshot**.
6. Enter a **reason for deletion** (required; 10–150 characters).
7. Click **Delete**.

---

## After deletion

- Snapshots are **temporarily deleted**. They can be recovered within the configurable rollback window using [Rollback Actions](GWS-06-04-rollback.md).
- After the rollback window expires, deletion is **permanent**.
- Rollback Actions require the **Security Essentials** license (Druva Public Cloud only). Contact Support to obtain this license.

---

## Related articles

- [Rollback Deleted Devices and Snapshots](GWS-06-04-rollback.md)
- [Enable, Disable, or Delete Gmail and Google Drive Data](GWS-06-01-enable-disable-delete-gmail-drive.md)
- [Manage and Delete Shared Drives](GWS-06-02-manage-shared-drives.md)
