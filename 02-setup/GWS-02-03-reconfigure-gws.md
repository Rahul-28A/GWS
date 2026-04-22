# Reconfigure or Reconnect Google Workspace

**Article ID:** GWS-02-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Reconfigure your Google Workspace connection when the app shows **Not Connected**, when the Super Admin account credentials have changed, or when you need to update the authorized domain. Reconfiguration stops all in-progress backups and re-establishes the OAuth connection.

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- You have access to the **Google Super Administrator** account.
- Your browser has **only one Google account** signed in.
- If the cause is an Advanced Protection policy error, resolve it first — see [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md).

> **⚠️ Important**  
> Reconfiguration stops all ongoing Google Workspace backups. Scheduled backups resume automatically after reconfiguration is complete.

---

## When to reconfigure

Reconfigure Google Workspace if you see any of the following:

- App status shows **Not Connected** on the Google Workspace Overview page.
- Backups fail with `EPERMS` (permission denied) errors across all users.
- You changed the Super Admin account used for Druva integration.
- You need to change the authorized Google Workspace domain.
- After following the steps in [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md) and the issue persists.

---

## Reconfigure Google Workspace

1. Sign in to the **Druva Cloud Platform Console**.
2. Click the **hamburger menu (☰)** and select **SaaS Apps > Google Workspace**.  
   The **Google Workspace Overview** page appears.
3. Click **Overview > Re-Configure**.
4. On the confirmation dialog, click **Yes**.
5. On the Google sign-in page, select or sign in with the **Google Super Administrator** account.
6. Click **Allow** to grant Druva access to your Google admin account and associated user data.
7. On the **Google Workspace Marketplace** page, click **Admin Install**.

> **📝 Note**  
> Because inSync for Google Workspace was previously installed, Druva skips directly to the **Manage Cloud App Accounts** page after you click Admin Install. You do not need to go through the full Marketplace installation again.

Druva reconnects to your Google Workspace admin account and resumes access to all associated users' data.

> **📝 Note**  
> If the page does not redirect to the Druva portal after reconfiguration, refresh the browser and check the app status on the Google Workspace Overview page.

---

## Verify the reconnection

After reconfiguring, confirm the connection is healthy:

1. Go to **Google Workspace > Overview**.
2. Check that **App Status** shows **Connected**.
3. Check **Last Configured** shows a recent timestamp.
4. Run an on-demand backup for one user to confirm data access is restored — see [Run an On-Demand Backup](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md).

---

## Related articles

- [Connect Druva to Google Workspace (Initial Setup)](GWS-02-01-connect-druva-to-gws.md)
- [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
- [Navigate the Google Workspace Overview Dashboard](../05-monitor/GWS-05-01-overview-dashboard.md)
