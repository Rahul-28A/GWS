# Configure User Mapping and Custom Domains

**Article ID:** GWS-02-02  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

By default, Druva maps each inSync user to their Google Workspace account using their email address. If your organization uses Active Directory (AD), LDAP, or a custom email domain, you need to configure the mapping method so Druva can correctly associate users with their Google Workspace accounts.

Incorrect mapping causes backups to fail with a `USER NOT FOUND` error.

---

## Before you begin

- You have completed [Connect Druva to Google Workspace](GWS-02-01-connect-druva-to-gws.md).
- You have the **Druva Cloud Administrator** role.
- If using the AD attribute method, you must have Active Directory or LDAP integrated with inSync.

---

## Understand the mapping methods

| Method | When to use | How it works |
|--------|-------------|--------------|
| **inSync Email ID** (default) | Your inSync user email matches the user's Google Workspace email | Direct email address match |
| **AD Attribute (UPN)** | You manage users through Active Directory or LDAP | Druva reads the User Principal Name (UPN) from your configured AD/LDAP mapping to identify users |

See [User Mapping Logic](../09-concepts/GWS-C-05-user-mapping-logic.md) for a detailed explanation of each method.

---

## Change the user mapping method

Only Cloud Administrators can change this setting.

1. Sign in to the **Druva Cloud Platform Console**.
2. Click the **hamburger menu (☰)** and select **SaaS Apps > Google Workspace**.
3. On the **Overview** page, click **Settings**.  
   The **Cloud App Settings** dialog appears.
4. Under the user mapping option:
   - Select **inSync Email ID** to use email address matching (default).
   - Select **AD Attribute** to use User Principal Name from your AD/LDAP integration.
5. Click **OK**.

---

## Configure a custom domain

Use this setting when your organization's inSync user email domain is different from the Google Workspace domain. For example, if inSync users have `@company.com` emails but Google Workspace uses `@company.workspace.com`.

Without this setting, Druva cannot find the correct Google account and backups fail with `USER NOT FOUND`.

1. Sign in to the **Druva Cloud Platform Console**.
2. Click the **hamburger menu (☰)** and select **SaaS Apps > Google Workspace**.
3. On the **Overview** page, click **Settings**.  
   The **Cloud App Settings** dialog appears.
4. In the **User custom domain** field, enter the Google Workspace domain (for example, `company.workspace.com`).  
   Druva replaces the inSync user's existing domain with this value when looking up their Google account.
5. Click **OK**.

> **📝 Note**  
> The custom domain must be unique and valid. Druva uses it only for Google Workspace account lookups — it does not change how users sign in to Druva.

---

## Add users to the backup profile

After configuring the mapping method, add users to a Profile that has Google Workspace (SaaS Apps) enabled. The method for adding users depends on your mapping configuration:

| Mapping method | How to add users |
|---------------|-----------------|
| **inSync Email ID** | Add users individually or import from a CSV file. See [Add Users Individually](https://help.druva.com/en/articles/8702659-add-users-individually) or [Import from CSV](https://help.druva.com/en/articles/8702660-add-a-group-of-users-by-importing-information-from-a-csv-file). |
| **AD Attribute** | Users are automatically imported and mapped via your AD/LDAP integration. No manual action required after the first sync. |

> **📝 Note**  
> If you haven't created a SaaS Apps-enabled Profile yet, you can add users to the Default Profile and then enable SaaS Apps for that Profile.

---

## Set up alerts for connection status changes

Druva can notify administrators when a Google Workspace app's connection status changes (for example, if it shows **Not Connected**).

1. In the **Druva Console**, click the **bell icon (🔔)** in the top navigation.
2. Click the **Alert Subscriptions** tab.
3. Select **SaaS Apps Status**, then click **Edit**.
4. In the **Admins to be notified** field, select the administrators who should receive alerts.
5. To also notify end users, select the **Notify user** checkbox.
6. Click **Save**.

---

## Related articles

- [Connect Druva to Google Workspace](GWS-02-01-connect-druva-to-gws.md)
- [User Mapping Logic](../09-concepts/GWS-C-05-user-mapping-logic.md)
- [Set Up Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md)
- [Troubleshoot Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
- [Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md)
