# Rollback Deleted Devices and Snapshots

**Article ID:** GWS-06-04  
**Audience:** Druva Cloud Administrators  
**License:** Security Essentials license required. For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

When you delete a Google Workspace user account, a Gmail device, a Google Drive device, a Shared Drive, or a snapshot, Druva temporarily holds the deleted item in a **Rollback Actions** queue before permanently removing it. You can undo the deletion within this window.

> **📝 Note**  
> Rollback Actions are available for **Druva Public Cloud** customers only and require the **Security Essentials** license. Contact Druva Support to obtain this license.

---

## How the rollback window works

After you delete a device, user, or snapshot:

1. The item moves to the **Rollback Actions** queue.
2. The rollback window begins (duration is configurable by your Druva administrator).
3. If you take no action, the item is **permanently deleted** when the window expires.
4. If you click **Rollback** within the window, the deletion is undone and the item is restored to its previous state.

---

## Access Rollback Actions

1. Sign in to the **Druva Cloud Platform Console**.
2. Navigate to **Rollback Actions** (available in the main navigation or admin settings).
3. Find the deleted item and click **Rollback**.

For full instructions, see [Rollback Actions](https://help.druva.com/en/articles/8513196-rollback-actions).

---

## When you cannot roll back

Rollback is blocked in the following scenarios. If you encounter one of these, contact Druva Support.

| Scenario | Why rollback is blocked | Resolution |
|---------|------------------------|-----------|
| The **user or profile is deleted** | The user or profile that owned the device no longer exists | Roll back the deleted user or profile first, then roll back the device |
| The **user's profile was changed** after deletion | The device's current profile doesn't match the one at time of deletion | Reassign the user to the previous profile |
| **Active license limit reached** | No available licenses to reactivate the user | Contact Support to procure additional licenses |
| **Shared Drive re-discovered** after deletion | The same Shared Drive was added again while the deletion was pending | Cannot be rolled back; manage the newly discovered drive instead |
| **Snapshot deleted twice** | A snapshot was deleted from both the main interface and from Rollback Actions | Deletion is permanent; cannot be undone |

---

## Related articles

- [Enable, Disable, or Delete Gmail and Google Drive Data](GWS-06-01-enable-disable-delete-gmail-drive.md)
- [Manage and Delete Shared Drives](GWS-06-02-manage-shared-drives.md)
- [Delete Snapshots](GWS-06-03-delete-snapshots.md)
- [Understand License Consumption](../05-monitor/GWS-05-04-license-consumption.md)
