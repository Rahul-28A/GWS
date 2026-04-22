# Troubleshoot Google Workspace Backup Errors

**Article ID:** GWS-08-01  
**Audience:** Druva Cloud Administrators, Support teams  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Use this guide to diagnose and resolve common errors that appear in the Google Workspace dashboard or backup job logs. Find your error code or status message in the sections below.

For a list of platform-level known issues, see [Known Issues and Limitations](GWS-08-04-known-issues.md).

---

## EPERMS — Permission Denied

This error appears when Druva lacks the administrative authority to access the Google Workspace tenant. It typically affects all users simultaneously.

### Root causes

- The account used for Druva integration does not have the **Google Super Administrator** role.
- The Druva app (inSync for Google Workspace) is restricted to specific Organizational Units (OUs) rather than the entire domain.
- OAuth consent was incomplete, or the admin was signed into **multiple Google accounts** during setup.

### Resolution

**1. Verify the administrator role**

In the [Google Admin Console](https://admin.google.com):
- Go to **Directory > Users**.
- Confirm the account used for Druva integration has the **Super Admin** role assigned, not just a custom admin role.

**2. Enable the Druva app for all users**

In the Google Admin Console:
- Go to **Apps > Google Workspace Marketplace apps > Apps list**.
- Select **Druva inSync for Google Workspace**.
- Under **User Access**, verify the status is **ON for everyone** (not restricted to specific OUs).

**3. Re-authenticate with a clean browser session**

- Sign out of all Google accounts in your browser.
- Sign back in using **only** the Super Administrator account.
- Reconfigure the Druva app — see [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md).
- When prompted, grant **all permissions** listed under the OAuth consent screen for the Druva app.

---

## EAUTH — Authorization Failed (Shared Drives)

This error is specific to Shared Drive backups and indicates a membership or permissions problem within the drive itself.

### Root causes and fixes

| Cause | Symptom | Fix |
|-------|---------|-----|
| No active member in the Shared Drive | EAUTH on a specific drive; all members are deleted or suspended | Add at least one active (non-suspended) user or Google Group as a member of the drive |
| Druva sync account lacks Content Manager or Manager role | EAUTH on specific drives only | Verify that at least one member has the **Manager** or **Content Manager** role |
| Druva app not enabled for the drive's OU | EAUTH on drives in specific OUs only | In Google Admin Console, confirm the app is enabled for all relevant OUs |

---

## No Content Backed Up Yet

This status message appears in the Shared Drives dashboard. It is a **configuration state**, not an active failure.

| Scenario | What it means | Resolution |
|---------|--------------|-----------|
| **Not Configured** | The drive has been discovered but has no storage or backup frequency assigned | Open the drive in the Shared Drives tab and complete the configuration — see [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md) |
| **Pending initial backup** | The drive is configured but the first scheduled backup has not run yet | Click **Backup Now** to trigger the first backup immediately |

---

## Backup Throttled

Druva's backup was rate-limited by the Google API. This status typically resolves automatically on the next scheduled backup cycle.

**If throttling persists across 3 or more consecutive backup cycles:**
- Contact Druva Support — persistent throttling may indicate an API quota issue with your Google Workspace account.

---

## USER NOT FOUND

This error means the inSync user ID does not match any account in the connected Google Workspace domain. It appears in **Status Details** for affected users.

### Root cause

Your organization uses a **custom email domain** for Google Workspace that differs from the domain used for inSync user accounts. For example, inSync users have `@company.com` emails but Google Workspace uses `@company.workspace.com`.

### Resolution

1. Navigate to **Google Workspace > Settings > Cloud App Settings**.
2. Enter the correct Google Workspace domain in the **User custom domain** field.
3. Click **OK**.

Full instructions: [Configure User Mapping and Custom Domains](../02-setup/GWS-02-02-user-mapping-custom-domains.md).

---

## Gmail backup fails — Google account quota exhausted

### Cause

Google Calendar attachments are stored in the user's Google Drive. If a user's Google Drive storage quota is full, Druva cannot back up calendar event attachments, and subsequent Gmail backups fail.

### Resolution

1. Ask the user to free up space in their Google Drive.
2. Alternatively, purchase additional Google Workspace storage for the affected user.
3. Re-run the backup after the quota is resolved — see [Run an On-Demand Backup](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md).

---

## Files skipped during backup

Individual files may be skipped without causing the entire backup to fail. Skipped files appear in the **Status Details** column.

| Cause | Detail | Workaround |
|-------|--------|-----------|
| File name too long | File names longer than **1,024 characters** cannot be backed up | Rename the file with a shorter name |
| Google Slides / PPTX > 400 MB | Large files may time out during the Google API download phase | Split into smaller files or convert to PDF — see [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md) |
| Unsupported native MIME type | Google Forms, Google Sites, and other unsupported types are always skipped | This is expected behavior — see [Supported MIME Types](../09-concepts/GWS-C-02-mime-types.md) |
| Google Doc comments | Some comments are skipped due to Google API limitations | Known limitation; no workaround available |

---

## Backup fails for archived users

Druva does not support backup of **archived user data** due to a Google API limitation. If a backup is failing for an archived user account, this is expected behavior and cannot be resolved.

---

## Related articles

- [Fix Google Workspace Connection Errors](GWS-08-03-fix-connection-errors.md)
- [Force Sync of Google Shared Drives](GWS-08-02-force-sync-shared-drives.md)
- [Known Issues and Limitations](GWS-08-04-known-issues.md)
- [Reconfigure or Reconnect Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md)
- [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md)
