# Fix Google Workspace Connection Errors

**Article ID:** GWS-08-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Use this guide if you encounter errors during the initial Google Workspace connection or reconfiguration — including OAuth authorization failures, Advanced Protection blocks, and app distribution errors.

For errors that appear after connection (backup failures, EPERMS, EAUTH), see [Troubleshoot Google Workspace Backup Errors](GWS-08-01-troubleshoot-backup-errors.md).

---

## Error 400: policy_enforced (Advanced Protection)

### What you see

```
Authorization Error
Error 400: policy_enforced
Advanced Protection prevented your Google Account from signing in.
```

### Cause

Your Google Super Administrator account has **Advanced Protection** enabled, which blocks most third-party OAuth apps — including Druva — from accessing the account by default.

### Resolution

You need to configure Druva as a trusted third-party app in the Google Admin Console before retrying the Druva connection.

1. In the [Google Admin Console](https://admin.google.com), go to **Security > Access and data control > App access control**.
2. Click **Manage Third-Party App Access**.
3. Click **Add app** under Configured apps.
4. Choose **OAuth App Name or Client ID** (or Android / iOS).
5. Search for **Druva inSync** by app name or Client ID and click **Search**.
6. Point to the app and click **Select**.
7. Check the boxes for the Druva client IDs you want to configure.
8. Click **Select**.
9. Select **Trusted** and click **Configure**.

For reference, see [Google's official guide](https://support.google.com/a/answer/7281227).

After completing these steps, return to the Druva Console and follow the standard [Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md) setup.

---

## OAuth failure — multiple Google accounts active

### What you see

An OAuth error or account selection confusion during the authorization step, or the inSync app cannot be installed.

### Cause

Your browser has **more than one Google account** signed in. Google presents all accounts and Druva may authenticate with the wrong one (not the Super Admin), causing the integration to fail.

### Resolution

1. Sign out of **all** Google accounts in your browser.
2. Clear browser cookies for `accounts.google.com` if the issue persists.
3. Sign in with **only** the Super Administrator account.
4. Retry the Druva configuration — see [Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md).

---

## App not redirecting after reconfiguration

### What you see

After completing reconfiguration, the browser stays on the Google or Marketplace page and does not redirect back to the Druva Console.

### Resolution

1. Manually navigate back to the Druva Console.
2. Go to **Google Workspace > Overview** and check **App Status**.
3. If status shows **Connected**, the reconfiguration succeeded — the redirect failure was cosmetic.
4. If status shows **Not Connected**, retry reconfiguration — see [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md).

---

## App shows "Not Connected" after setup

### Cause

The OAuth token has expired, the Super Admin account credentials changed, or the Druva app was removed from the Google Workspace Marketplace by an admin.

### Resolution

Reconfigure Google Workspace — see [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md).

---

## Related articles

- [Connect Druva to Google Workspace (Initial Setup)](../02-setup/GWS-02-01-connect-druva-to-gws.md)
- [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md)
- [Troubleshoot Google Workspace Backup Errors](GWS-08-01-troubleshoot-backup-errors.md)
