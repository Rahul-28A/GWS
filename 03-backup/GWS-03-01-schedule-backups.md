# Schedule Google Workspace Backups

**Article ID:** GWS-03-01  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva backs up Google Workspace data automatically on a schedule you define in a **Profile**. A Profile is a collection of backup, retention, and privacy settings that you assign to users. To start scheduled backups, you need to either create a new Profile with Google Workspace enabled or update an existing one.

---

## Before you begin

- You have completed [Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md).
- Users are imported into Druva (via Google Directory, AD/LDAP, or manually).
- At least one Google Workspace device must be online for scheduled backups to run.

---

## Step 1 — Enable Google Workspace in a Profile

1. Sign in to the **Druva Cloud Platform Console**.
2. Navigate to the Profile you want to update, or [create a new Profile](https://help.druva.com/en/articles/8998101-create-a-profile).
3. Within the Profile, click **SaaS Apps**, then click **Edit**.
4. On the **Edit SaaS Apps Configuration** page, select **Google Workspace**.
5. Select the checkboxes for the workloads you want to back up:
   - **Gmail** — backs up email, calendar events, and contacts.
   - **Google Drive** — backs up files, folders, and trash.
6. Click **Save**.

---

## Step 2 — Set the backup schedule

The backup schedule for Google Workspace is set at the Profile level under the SaaS Apps backup interval settings.

1. In the Profile, locate the **Backup Interval for SaaS Apps** setting.
2. Set the frequency (for example, every 12 hours, daily, or weekly).
3. Click **Save**.

For detailed instructions, see [Define the Backup Interval for SaaS Apps](https://help.druva.com/en/articles/8702806-define-the-backup-interval-and-the-schedule-user-devices-and-saas-apps).

---

## Step 3 — Assign users to the Profile

Users must be assigned to the Profile to have their data backed up. If users were imported during provisioning setup, they may already be assigned to a Profile.

To verify or change a user's Profile assignment, go to **Google Workspace > Users** and check the **Profile** column for each user.

---

## Backup policies that apply to Google Workspace data

The following policies, defined in the Profile, control how Google Workspace data is backed up and managed:

| Policy | What it controls | Where to configure |
|--------|-----------------|-------------------|
| **Backup policy** | How often Druva backs up SaaS Apps data | [Define the backup interval for SaaS Apps](https://help.druva.com/en/articles/8702806-define-the-backup-interval-and-the-schedule-user-devices-and-saas-apps) |
| **Retention policy** | How long backed-up snapshots are kept in storage | [Configure the backup retention policy](https://help.druva.com/en/articles/8367724-configure-the-backup-retention-policy) |
| **Data privacy policy** | Who in your organization can access backed-up user data | [Configure the user data privacy policy](https://help.druva.com/en/articles/8702770-configure-the-user-data-privacy-policy) |
| **Global exclusion policy** | File types and folders to exclude from all backups | [Configure the global exclude list](https://help.druva.com/en/articles/8702773-configure-the-global-exclude-list) |

See [Backup Policies for Google Workspace Data](GWS-03-04-backup-policies.md) for a full explanation of each policy.

---

## Important notes on scheduled backups

- **At least one Google Workspace device** must be online for scheduled backups to run.
- Archived user data and Google Vault data **cannot** be backed up due to Google API limitations.
- If a user's Google account **quota is exhausted**, backups of their calendar event attachments will fail because those attachments are stored in their Google Drive.
- If an individual folder and a Shared folder have the **same name**, Druva renames the Shared folder as `<folder name> <internal ID>` during backup. Your personal folder name is not changed.

---

## Verify backups are running

After enabling the Profile, check that backups are running:

1. Go to **Google Workspace > Overview Dashboard**.
2. Look at the **Workloads** section — Gmail and Google Drive should show a recent **Last Completed Backup** timestamp.
3. For detailed status, see [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md).

---

## Related articles

- [Run an On-Demand Backup of Gmail or Google Drive](GWS-03-02-on-demand-backup-gmail-drive.md)
- [Backup Policies for Google Workspace Data](GWS-03-04-backup-policies.md)
- [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
