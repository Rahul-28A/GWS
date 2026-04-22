# Run an On-Demand Backup of Shared Drives

**Article ID:** GWS-03-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

You can trigger an immediate backup for any configured Shared Drive without waiting for the next scheduled run.

---

## Before you begin

- The Shared Drive is configured with a storage assignment and backup frequency. If status shows **Not Configured**, complete the setup in [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md) first.
- The Shared Drive's App Status is **Enabled**.
- The Shared Drive has at least one active member.

---

## Run the backup

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Shared Drives** tab.
3. Click the name of the Shared Drive you want to back up.
4. Click the **three-dot menu (⋮)** and select **Backup Now**.

Druva initiates the backup. After completion, the **Backup Status** on the Shared Drive page updates to **Backed Up Successfully**.

---

## Track backup progress

- Go to **inSync Management Console > Jobs** to see the backup job status.
- Click the **Activity Stream** tab on the Shared Drive page to view backup activity logs.

> **📝 Note — Activity log retention**  
> Backup activity logs older than 30 days are automatically deleted when the monthly count exceeds 30. Download and restore activity logs are kept indefinitely.

---

## Related articles

- [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)
- [Monitor Shared Drives Backup Status](../05-monitor/GWS-05-03-monitor-shared-drives.md)
- [Restore Shared Drives Data](../04-restore/GWS-04-03-restore-shared-drives.md)
- [Force Sync of Google Shared Drives](../08-troubleshoot/GWS-08-02-force-sync-shared-drives.md)
