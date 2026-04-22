# Set Up Google Directory User Provisioning

**Article ID:** GWS-02-05  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Google Directory integration lets Druva automatically import users from your Google Workspace organization and keep them in sync. When users are added, suspended, or removed in Google Directory, Druva reflects those changes — eliminating the need for manual user management.

This guide walks through the full setup from connecting your tenant to syncing users.

---

## Before you begin

- You have completed [Connect Druva to Google Workspace](GWS-02-01-connect-druva-to-gws.md).
- You have the **Druva Cloud Administrator** role.
- If you are switching from another provisioning method (AD/LDAP, SCIM, Azure AD), see [Change the User Provisioning Method](GWS-02-07-change-provisioning-method.md) first.

---

## Step 1 — Register your Google Workspace tenant

If you have already connected Druva to Google Workspace (GWS-02-01), your tenant is already registered. Proceed to Step 2.

If you have not yet connected Druva, follow [Connect Druva to Google Workspace](GWS-02-01-connect-druva-to-gws.md) first.

---

## Step 2 — Enable Cloud Key Management (KMS)

KMS must be enabled for scheduled user imports and backups to run. By default, KMS is enabled for data protection when you first connect Google Workspace.

If KMS is not yet enabled:

1. In the Druva Console, go to **Settings > Cloud Key Management Service**.
2. Click **Enable KMS**.

> **⚠️ Important**  
> Once KMS is enabled, it **cannot be disabled**. Backups cannot run without KMS enabled.

---

## Step 3 — Select Google Directory as the provisioning method

1. In the Druva Console, go to **Google Workspace > Users**.
2. Click the **User Provisioning** tab.
3. Under **User Provisioning Method**, select **Use Google Directory**.
4. On the confirmation dialog, click **Continue**.
5. Click **Save**.

---

## Step 4 — Create user mappings

Mappings control which Google Workspace users are imported into Druva, which Profile they are assigned to, and where their backup data is stored.

1. On the **Google Directory Provisioning** page, click **New Mapping**.
2. Enter a **name** for the mapping.
3. Select the **filter** for importing users:
   - **Groups** — Import users from specific Google Groups.
   - **All Users** — Import all users in your Google Workspace organization.
4. Select the **storage region** where user data will be saved.
5. Select the **Profile** to assign imported users to.
6. Click **Save**.

A confirmation message appears: "Mapping successfully created."

> **📝 Note**  
> Users who are suspended or archived in Google Directory cannot be imported. They will be skipped during sync.

You can create multiple mappings to assign different user groups to different Profiles or storage regions. See [Manage Google Directory Mappings](GWS-02-06-manage-directory-mappings.md) for how to prioritize and manage mappings.

---

## Step 5 — Sync users

After creating mappings, sync users to import them into Druva.

### Auto-sync (recommended)

Once mappings are created, Druva automatically:
- Imports new users added to Google Directory within 24 hours.
- Updates user details for users managed via Google Directory.
- Preserves or reactivates users when their Google Directory status changes.

No additional action is required for auto-sync.

### On-demand sync

To sync immediately without waiting for the scheduled auto-sync:

1. Go to **Google Workspace > Users > User Provisioning**.
2. In the **Summary** section, click the **three-dot menu (⋮)**.
3. Select **Sync Users**.

Druva imports users based on your configured mappings. **Last Sync Time** updates when the sync completes.

> **📝 Note**  
> You must have at least one active inSync product license to use the sync users functionality.

---

## When users are automatically preserved

Regardless of your auto-preserve setting, Druva preserves active users if any of the following happen in Google Directory:

- The user is removed from all mapped Google Groups.
- The user is suspended in Google Directory.
- The user is archived in Google Directory.

---

## Enable auto-preserve for unmapped users

Auto-preserve is disabled by default. When enabled, Druva automatically moves users to a **Preserved** state when they no longer match any active mapping (instead of leaving them in Active state).

1. Go to **Google Workspace > Users > User Provisioning**.
2. Click the **three-dot menu (⋮)** in the Summary section.
3. Select **Edit**.
4. In the **Google Workspace Settings** window, select **Auto preserve unmapped users**.
5. Click **Save**.

---

## Import individual users manually

You can also import specific users directly from Google Directory without creating a mapping:

1. Go to **Google Workspace > Users**.
2. Click **Import > Import Users from Google Directory**.
3. In the **Import Users** window:
   - Search for and select users by **Email Address**.
   - Select **Storage** and **Profile** for the imported users.
   - Optionally select **Send activation email to newly added users**.
4. Click **Save**.

---

## What to do after provisioning

To start backing up imported users' data, enable Google Workspace in their assigned Profile:

- See [Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md) for instructions.

---

## Related articles

- [Manage Google Directory Mappings](GWS-02-06-manage-directory-mappings.md)
- [Change the User Provisioning Method](GWS-02-07-change-provisioning-method.md)
- [Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md)
- [User Mapping Logic](../09-concepts/GWS-C-05-user-mapping-logic.md)
