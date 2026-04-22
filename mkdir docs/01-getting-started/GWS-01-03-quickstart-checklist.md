# Quick-Start Checklist: Protect Google Workspace in 5 Steps

**Article ID:** GWS-01-03  
**Audience:** Administrators setting up Druva for the first time  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Use this checklist to set up Google Workspace backup from scratch. Each step links to the full guide for that task. Complete the steps in order — each step depends on the previous one.

**Estimated total time:** 45–90 minutes (first-time setup)

---

## Before you begin

Confirm you have the following before starting:

- [ ] A Druva account with the **Cloud Administrator** role
- [ ] A **Google Super Administrator** account (not a delegated admin)
- [ ] One of the supported Google Workspace editions: Business Starter, Standard, Plus, or Enterprise
- [ ] A browser session with **only one Google account** signed in (multiple sessions cause OAuth failures)
- [ ] Cloud Key Management (KMS) enabled or AWS KMS credentials ready

---

## Step 1 — Connect Druva to Google Workspace

Authorize Druva to access your Google Workspace organization using OAuth and install the inSync app via Google Workspace Marketplace.

**Who does this:** Google Super Administrator + Druva Cloud Administrator (can be the same person)  
**Time:** 15–20 minutes

➡️ **[Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md)**

**Done when:** The Google Workspace Overview page shows App Status as **Connected**.

---

## Step 2 — Set up user provisioning

Import your Google Workspace users into Druva so their data can be backed up. Choose the provisioning method that matches your organization's identity management setup.

**Who does this:** Druva Cloud Administrator  
**Time:** 10–30 minutes (depending on method)

| Your setup | Use this method |
|-----------|----------------|
| Google Directory | ➡️ [Set Up Google Directory User Provisioning](../02-setup/GWS-02-05-google-directory-provisioning.md) |
| Active Directory / LDAP | Configure AD/LDAP mapping (see AD/LDAP documentation) |
| Manual (small teams) | Add users individually via the Druva Console |

**Done when:** Users appear in the Google Workspace > Users list with status **Active**.

---

## Step 3 — Configure backup profiles

A Profile defines what gets backed up and how often. Assign users to a Profile that has Google Workspace (SaaS Apps) enabled, and set your backup schedule and retention policy.

**Who does this:** Druva Cloud Administrator  
**Time:** 10–15 minutes

➡️ **[Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md)**

**Done when:** The Profile shows Gmail and/or Google Drive enabled under SaaS Apps, and a backup schedule is set.

---

## Step 4 — (Optional) Set up Shared Drives

If your organization uses Google Shared Drives (also called Team Drives), configure them for backup separately. Druva can auto-discover Shared Drives every 24 hours, or you can add them manually.

**Who does this:** Druva Cloud Administrator  
**Time:** 10–20 minutes

➡️ **[Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)**

**Done when:** Shared Drives appear in the Shared Drives tab with status **Enabled**.

---

## Step 5 — Verify your first backup

Run an on-demand backup to confirm everything is working before relying on the scheduled backup.

**Who does this:** Druva Cloud Administrator  
**Time:** 5 minutes to trigger; backup duration varies by data size

➡️ **[Run an On-Demand Backup of Gmail or Google Drive](../03-backup/GWS-03-02-on-demand-backup-gmail-drive.md)**

Then verify the result:

➡️ **[Navigate the Google Workspace Overview Dashboard](../05-monitor/GWS-05-01-overview-dashboard.md)**

**Done when:** The dashboard shows **Backed Up Successfully** for the users you tested.

---

## What to do next

Once backup is running, explore these capabilities:

- **Restore data** — [Restore Gmail Data](../04-restore/GWS-04-01-restore-gmail.md) | [Restore Google Drive Data](../04-restore/GWS-04-02-restore-drive.md)
- **Monitor health** — [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md)
- **Set up eDiscovery** — [Enable eDiscovery and Legal Hold](../07-compliance/GWS-07-01-ediscovery-legal-hold.md)
- **Troubleshoot issues** — [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)

---

## Related articles

- [Google Workspace Backup with Druva — Overview](GWS-01-01-overview.md)
- [Supported Google Workspace Editions and Data Types](GWS-01-02-supported-editions-data-types.md)
- [Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
