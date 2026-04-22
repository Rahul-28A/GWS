# Druva inSync — Google Workspace Documentation

This is the complete documentation set for protecting Google Workspace data with Druva inSync. Every article is organized by what you are trying to do, not by how the product is built internally.

**New to Druva?** Start with the [Quick-Start Checklist](01-getting-started/GWS-01-03-quickstart-checklist.md) — it links to every step you need in the right order.

---

## 01 · Getting Started

Understand what Druva protects and how to get started quickly.

| Article | Description |
|---------|-------------|
| [Google Workspace Backup with Druva — Overview](01-getting-started/GWS-01-01-overview.md) | What Druva backs up, how storage works, and where to begin |
| [Supported Google Workspace Editions and Data Types](01-getting-started/GWS-01-02-supported-editions-data-types.md) | Quick-reference tables for editions, data types, metadata, and exclusions |
| [Quick-Start Checklist: Protect Google Workspace in 5 Steps](01-getting-started/GWS-01-03-quickstart-checklist.md) | End-to-end setup checklist with links to every required step |

---

## 02 · Setup & Configuration

Connect Druva to Google Workspace, configure user provisioning, and set up Shared Drives.

| Article | Description |
|---------|-------------|
| [Connect Druva to Google Workspace (Initial OAuth Setup)](02-setup/GWS-02-01-connect-druva-to-gws.md) | Authorize Druva with a Google Super Admin account via OAuth |
| [Configure User Mapping and Custom Domains](02-setup/GWS-02-02-user-mapping-custom-domains.md) | Set the email or AD attribute mapping method; configure custom domains |
| [Reconfigure or Reconnect Google Workspace](02-setup/GWS-02-03-reconfigure-gws.md) | Re-establish the connection when the app shows Not Connected |
| [Set Up and Configure Shared Drives Backup](02-setup/GWS-02-04-shared-drives-setup.md) | Auto-configure or manually add Shared Drives for backup |
| [Set Up Google Directory User Provisioning](02-setup/GWS-02-05-google-directory-provisioning.md) | Import and sync users automatically from Google Directory |
| [Manage Google Directory Mappings and Auto-Preserve](02-setup/GWS-02-06-manage-directory-mappings.md) | Prioritize, edit, or delete provisioning mappings |
| [Change the User Provisioning Method](02-setup/GWS-02-07-change-provisioning-method.md) | Switch between Google Directory, Azure AD, SCIM, and AD/LDAP |

---

## 03 · Backup

Schedule backups, run on-demand backups, and understand backup policies.

| Article | Description |
|---------|-------------|
| [Schedule Google Workspace Backups](03-backup/GWS-03-01-schedule-backups.md) | Enable backup in a Profile and set the backup frequency |
| [Run an On-Demand Backup of Gmail or Google Drive](03-backup/GWS-03-02-on-demand-backup-gmail-drive.md) | Back up a specific user's data immediately |
| [Run an On-Demand Backup of Shared Drives](03-backup/GWS-03-03-on-demand-backup-shared-drives.md) | Trigger an immediate backup for a Shared Drive |
| [Backup Policies for Google Workspace Data](03-backup/GWS-03-04-backup-policies.md) | Understand frequency, retention, privacy, and exclusion policies |

---

## 04 · Restore & Download

Restore Gmail, Drive, and Shared Drives data, or download it to your device.

| Article | Description |
|---------|-------------|
| [Restore Gmail Data (Mail, Contacts, Calendar)](04-restore/GWS-04-01-restore-gmail.md) | Full mailbox or granular restore; restore to same or different user |
| [Restore Google Drive Data](04-restore/GWS-04-02-restore-drive.md) | Restore files and folders to Google Drive or a user's device |
| [Restore Shared Drives Data](04-restore/GWS-04-03-restore-shared-drives.md) | In-place or copy restore for Shared Drives |
| [Download Google Workspace Data](04-restore/GWS-04-04-download-gws-data.md) | Download Gmail, Drive, or Shared Drives data in Archive, PST, or MBOX format |

---

## 05 · Monitor & Report

Track backup health, license consumption, and reporting.

| Article | Description |
|---------|-------------|
| [Navigate the Google Workspace Overview Dashboard](05-monitor/GWS-05-01-overview-dashboard.md) | Understand every section of the Overview Dashboard |
| [Monitor Gmail and Google Drive Backup Status](05-monitor/GWS-05-02-monitor-gmail-drive.md) | Per-user backup status, error details, and actions |
| [Monitor Shared Drives Backup Status](05-monitor/GWS-05-03-monitor-shared-drives.md) | Per-drive backup status and activity logs |
| [Understand License Consumption](05-monitor/GWS-05-04-license-consumption.md) | Active vs. Preserved licenses — what they mean and how to manage them |
| [Google Workspace Reports — Overview and Access](05-monitor/GWS-05-05-reports-overview.md) | All available reports, how to access them, and API names |

---

## 06 · Manage Data

Enable, disable, delete, and recover Google Workspace backup data.

| Article | Description |
|---------|-------------|
| [Enable, Disable, or Delete Gmail and Google Drive Data](06-manage/GWS-06-01-enable-disable-delete-gmail-drive.md) | Control backup state and delete user data |
| [Manage and Delete Shared Drives](06-manage/GWS-06-02-manage-shared-drives.md) | Enable, disable, or permanently remove a Shared Drive from Druva |
| [Delete Snapshots (Gmail, Drive, Shared Drives)](06-manage/GWS-06-03-delete-snapshots.md) | Remove specific backup snapshots across all workloads |
| [Rollback Deleted Devices and Snapshots](06-manage/GWS-06-04-rollback.md) | Undo deletions within the rollback window |

---

## 07 · Compliance & eDiscovery

Place legal holds, access preserved data, and retrieve metadata for compliance workflows.

| Article | Description |
|---------|-------------|
| [Enable eDiscovery and Legal Hold for Google Workspace](07-compliance/GWS-07-01-ediscovery-legal-hold.md) | Set up legal hold policies to preserve data beyond normal retention |
| [Access Legal Hold Data via WebDAV](07-compliance/GWS-07-02-webdav-access.md) | Connect a WebDAV client to browse and export preserved data |
| [Retrieve Google Drive Metadata Attributes via WebDAV](07-compliance/GWS-07-03-metadata-webdav.md) | Configure your WebDAV client to retrieve extended Drive metadata |

---

## 08 · Troubleshoot

Diagnose and fix backup, restore, and connection errors.

| Article | Description |
|---------|-------------|
| [Troubleshoot Google Workspace Backup Errors](08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md) | EPERMS, EAUTH, USER NOT FOUND, throttling, and skipped files |
| [Force Sync of Google Shared Drives](08-troubleshoot/GWS-08-02-force-sync-shared-drives.md) | Trigger immediate Shared Drive discovery outside the 24-hour cycle |
| [Fix Google Workspace Connection Errors](08-troubleshoot/GWS-08-03-fix-connection-errors.md) | Advanced Protection errors, OAuth failures, redirect issues |
| [Known Issues and Limitations](08-troubleshoot/GWS-08-04-known-issues.md) | Canonical list of all known issues with workarounds |

---

## 09 · Concepts & Reference

Background reading and reference tables to understand how Druva works.

| Article | Description |
|---------|-------------|
| [Why Does Druva Show More Data Than Google Storage?](09-concepts/GWS-C-04-data-size-accounting.md) | Four reasons why Druva backup size is higher than Google's reported size |
| [Supported MIME Types for Google Workspace Backup](09-concepts/GWS-C-02-mime-types.md) | Complete list of supported and unsupported native Google MIME types |
| [File Size Limits and Workarounds](09-concepts/GWS-C-03-file-size-limits.md) | File size and name limits, with workarounds for each |
| [User Mapping Logic (Email ID vs. AD Attribute vs. UPN)](09-concepts/GWS-C-05-user-mapping-logic.md) | How Druva matches inSync users to Google Workspace accounts |

---

## 10 · Release Notes

| Article | Description |
|---------|-------------|
| [Release Notes — Druva for Google Workspace (Current)](10-release-notes/GWS-RN-01-release-notes-current.md) | Latest releases — October 2025 to present |
| [Archived Release Notes — 2025](10-release-notes/GWS-RN-ARCHIVE-2025.md) | Releases from January – October 2025 |
| [Archived Release Notes — 2024](10-release-notes/GWS-RN-ARCHIVE-2024.md) | Releases from January – September 2024 |
| [GovCloud Release Notes — Google Workspace](10-release-notes/GWS-RN-GOVCLOUD.md) | GovCloud-specific releases |

---

## Suggested learning paths

**Setting up Druva for the first time**
→ [Overview](01-getting-started/GWS-01-01-overview.md) → [Checklist](01-getting-started/GWS-01-03-quickstart-checklist.md) → [Connect](02-setup/GWS-02-01-connect-druva-to-gws.md) → [Provision users](02-setup/GWS-02-05-google-directory-provisioning.md) → [Schedule backup](03-backup/GWS-03-01-schedule-backups.md) → [Verify on dashboard](05-monitor/GWS-05-01-overview-dashboard.md)

**Restoring accidentally deleted emails**
→ [Restore Gmail](04-restore/GWS-04-01-restore-gmail.md) → [Monitor status](05-monitor/GWS-05-02-monitor-gmail-drive.md) → [Troubleshoot if needed](08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)

**Protecting Shared Drives for a new team**
→ [Set up Shared Drives](02-setup/GWS-02-04-shared-drives-setup.md) → [Run backup](03-backup/GWS-03-03-on-demand-backup-shared-drives.md) → [Monitor](05-monitor/GWS-05-03-monitor-shared-drives.md) → [Restore if needed](04-restore/GWS-04-03-restore-shared-drives.md)

**Investigating a backup failure**
→ [Overview Dashboard](05-monitor/GWS-05-01-overview-dashboard.md) → [Error codes](08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md) → [Connection errors](08-troubleshoot/GWS-08-03-fix-connection-errors.md) → [Known issues](08-troubleshoot/GWS-08-04-known-issues.md)

**Setting up eDiscovery for legal team**
→ [Legal Hold](07-compliance/GWS-07-01-ediscovery-legal-hold.md) → [WebDAV access](07-compliance/GWS-07-02-webdav-access.md) → [Metadata retrieval](07-compliance/GWS-07-03-metadata-webdav.md)
