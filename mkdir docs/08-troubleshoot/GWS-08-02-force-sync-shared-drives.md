# Force Sync of Google Shared Drives

**Article ID:** GWS-08-02  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva auto-discovers new Shared Drives every 24 hours. If metadata changes in Google Workspace — such as a drive rename or new drive creation — are not yet visible in the Druva Console, you can manually trigger an immediate discovery to sync the changes.

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- The Google Workspace app shows **Connected** status on the Overview page.

---

## Trigger a manual Shared Drives sync

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace**.
2. Click the **Shared Drives** tab.
3. Click the **three-dot menu (⋮)** in the top-right corner of the Shared Drives section.
4. Select **Discover Shared Drives**.
5. Wait for the discovery process to complete. Duration depends on the number of drives in your organization.
6. Refresh the page to verify that drive names and membership reflect your current Google Workspace environment.

**What this does:** Triggers an immediate metadata sync between Google Workspace and Druva, bypassing the standard 24-hour schedule.

---

## Sync is not updating — troubleshooting

If changes still do not appear after running discovery:

| Check | Action |
|-------|--------|
| **App connection status** | Confirm the Google Workspace app shows **Connected** on the Overview page |
| **App is disconnected** | Reconfigure the app — see [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md) |
| **Connection is healthy but data is missing** | Contact Druva Support |

---

## Related articles

- [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)
- [Monitor Shared Drives Backup Status](../05-monitor/GWS-05-03-monitor-shared-drives.md)
- [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md)
- [Troubleshoot Google Workspace Backup Errors](GWS-08-01-troubleshoot-backup-errors.md)
