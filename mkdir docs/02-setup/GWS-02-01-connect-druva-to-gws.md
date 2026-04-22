# Connect Druva to Google Workspace (Initial OAuth Setup)

**Article ID:** GWS-02-01  
**Audience:** Druva Cloud Administrators, Google Super Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Connect your Google Workspace organization to Druva inSync so that Druva can discover users and back up Gmail, Google Drive, and Shared Drives. This is a one-time setup that uses OAuth and the Google Workspace Marketplace.

| | |
|--|--|
| **Who does this** | Google Super Administrator + Druva Cloud Administrator |
| **Time required** | 15–20 minutes |
| **Done once or repeated** | Once (unless you need to [reconfigure](GWS-02-03-reconfigure-gws.md)) |

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- You are signed in as a **Google Super Administrator** — not a delegated admin.
- Your browser has **only one Google account** active. Multiple signed-in Google sessions cause the OAuth flow to fail.
- Your organization uses a [supported Google Workspace edition](../01-getting-started/GWS-01-02-supported-editions-data-types.md).

> **⚠️ Important**  
> If your organization has **Advanced Protection** enabled on the Super Admin account, you will see `Error 400: policy_enforced` during Step 2. Stop and follow [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md) before continuing.

---

## Step 1 — Open the Google Workspace integration page

1. Sign in to the **Druva Cloud Platform Console**.
2. Click the **hamburger menu (☰)** in the top navigation bar.
3. Select **SaaS Apps > Google Workspace**.  
   The **Add Google Workspace Account** page appears.
4. Click **Add Google Workspace Account**.
5. On the confirmation dialog, click **Configure**.

---

## Step 2 — Sign in with Google and grant access

1. On the Google sign-in page, enter your **Super Administrator** email address and password.
2. Click **Next**.
3. On the permissions page, click **Allow** to grant Druva access to your admin account and the user data associated with your account.

> **📝 Note**  
> If you see an authorization error at this step, your Super Admin account may have Advanced Protection enabled. See [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md).

---

## Step 3 — Install the Druva app from Google Workspace Marketplace

1. On the **Google Workspace Marketplace** page, click **Admin Install**.
2. On the domain-wide install confirmation dialog, click **Continue**.
3. In the **inSync for Google Workspace** dialog:
   - From the **Turn ON for** list, select the domain you want to protect.
   - Select the **terms of service** checkbox.
   - Click **Accept**.
4. When the installation confirmation appears, click **Done**.

> **📝 Note**  
> If you had previously installed the inSync app, Druva skips the Marketplace step and goes directly to the management console.

---

## Step 4 — Verify the connection

After installation, Druva redirects you to the inSync Management Console.

1. On the **Verify Configuration** dialog that appears, type the **email address** of any user in your organization in the **Select a user** field.
2. Click **Verify**.

A success confirmation means Druva can access your Google Workspace data.

> **📝 Note**  
> Enter an email address in this field. User Principal Name (UPN) is not supported at the verification step.

---

## What happens next

- Druva discovers all Google Workspace users associated with your admin account.
- The Google Workspace Overview page shows your app status as **Connected**.
- You can now set up user provisioning and enable backups.

**Next steps:**

1. Set up user provisioning — choose from [Google Directory](GWS-02-05-google-directory-provisioning.md), AD/LDAP, or manual import.
2. [Configure user mapping and custom domains](GWS-02-02-user-mapping-custom-domains.md) if your organization uses a custom email domain.
3. [Enable backup in a Profile](../03-backup/GWS-03-01-schedule-backups.md).

---

## Related articles

- [Configure User Mapping and Custom Domains](GWS-02-02-user-mapping-custom-domains.md)
- [Reconfigure or Reconnect Google Workspace](GWS-02-03-reconfigure-gws.md)
- [Set Up Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md)
- [Fix Google Workspace Connection Errors](../08-troubleshoot/GWS-08-03-fix-connection-errors.md)
- [Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md)
