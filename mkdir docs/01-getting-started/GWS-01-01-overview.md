# Google Workspace Backup with Druva — Overview

**Article ID:** GWS-01-01  
**Audience:** Administrators, IT managers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva inSync protects your organization's Google Workspace data by backing up **Gmail**, **Google Drive**, and **Shared Drives** to the Druva Cloud. If data is accidentally deleted, corrupted, or lost due to a ransomware attack, you can restore it to its original location or to a different account — without relying on Google's native retention policies.

This article explains what Druva protects, how backup storage works, and where to start.

---

## What Druva backs up

### Gmail

Druva backs up the following Gmail data for each user:

| Data type | What's included |
|-----------|----------------|
| **Emails** | Message body and all attachments |
| **Calendar events** | Event details and links to Drive attachments |
| **Contacts** | All contacts, including Other Contacts (limited fields — see note below) |

**Gmail metadata captured:**

- Email: To, From, Cc, Bcc, Subject, Sent On, Received On
- Attachments: Name, Size
- Timestamps: Created, Modified, Received, Sent
- Labels

> **📝 Note — Other Contacts field limitation**  
> Due to Google People API restrictions, Other Contacts are backed up with only three fields: Name, Phone Number, and Email Address. Backup and restore of Other Contacts is **not supported on GovCloud**.

### Google Drive

Druva backs up the following Drive data for each user:

| Data type | What's included |
|-----------|----------------|
| **Files and folders** | Files owned by the user, or shared with the user with download permission |
| **Trash** | Files in the user's trash at backup time |
| **Comments** | File comments (subject to Google API availability — some may be skipped) |

**Google Drive metadata captured:**

Title, Description, Created Date, Modified Date, File Size, Original Filename, Owners, Last Modifying User, MD5 Checksum

### Shared Drives

Druva backs up Shared Drive contents including files, folders, member details, access rights, settings, themes, and trash. See [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md) for the full data list.

---

## Native Google file types backed up

Druva backs up the following native Google file formats. All other native Google file types (including Google Forms and Google Sites) are skipped.

| MIME type | File format |
|-----------|-------------|
| `application/vnd.google-apps.document` | Google Docs |
| `application/vnd.google-apps.spreadsheet` | Google Sheets |
| `application/vnd.google-apps.presentation` | Google Slides |
| `application/vnd.google-apps.drawing` | Google Drawings |

Non-native files (PDFs, Office files, images, etc.) are backed up as-is regardless of format.

See [Supported MIME Types for Google Workspace Backup](../09-concepts/GWS-C-02-mime-types.md) for the complete reference.

---

## How backup storage works

> **📝 Note — Storage quota**  
> Google Workspace backup data consumes your **Organization Quota** in Druva, not individual user backup quotas.

Druva performs an **incremental forever** backup strategy:

1. The first backup is a full backup of all supported data.
2. Every subsequent backup captures only changed data.
3. Druva retains snapshots according to the retention policy defined in your Profile.

Because Druva retains deleted files until the retention period expires, the backup size shown in Druva will typically be **higher** than the storage usage shown in Google. See [Why Does Druva Show More Data Than Google Storage?](../09-concepts/GWS-C-04-data-size-accounting.md) for a full explanation.

---

## What's not backed up

| Excluded item | Reason |
|--------------|--------|
| Google Forms | Not supported by Druva |
| Google Sites | Not supported by Druva |
| My Computer folder | Local sync folder — only My Drive and Shared Drives are protected |
| Archived user data | Google API limitation |
| Google Vault data | Google API limitation |
| Birthday and Task calendars | Google API limitation |
| Google Slides / PPTX files > 400 MB | Google infrastructure limit — see [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md) |

---

## Supported Google Workspace editions

Druva inSync supports the following Google Workspace editions:

- Business Starter
- Business Standard
- Business Plus
- Enterprise

---

## How user mapping works

Druva maps each inSync user to their Google Workspace account using one of two methods:

- **Email address** — Direct match between the inSync user email and the Google Workspace account email. This is the default.
- **User Principal Name (UPN)** — Mapping via a configured Active Directory (AD) attribute, used when your organization manages users through AD/LDAP.

See [User Mapping Logic](../09-concepts/GWS-C-05-user-mapping-logic.md) for a detailed explanation of how each method works and when to use it.

---

## How to get started

Use this path to set up Google Workspace backup from scratch:

1. **[Quick-Start Checklist](GWS-01-03-quickstart-checklist.md)** — Confirm prerequisites and follow the end-to-end setup sequence.
2. **[Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md)** — Authorize Druva with a Google Super Admin account.
3. **[Schedule Backups](../03-backup/GWS-03-01-schedule-backups.md)** — Enable backup in a Profile and set your backup frequency.
4. **[Monitor the Dashboard](../05-monitor/GWS-05-01-overview-dashboard.md)** — Verify backups are running successfully.

---

## Related articles

- [Supported Google Workspace Editions and Data Types](GWS-01-02-supported-editions-data-types.md)
- [Quick-Start Checklist](GWS-01-03-quickstart-checklist.md)
- [Connect Druva to Google Workspace](../02-setup/GWS-02-01-connect-druva-to-gws.md)
- [Why Does Druva Show More Data Than Google Storage?](../09-concepts/GWS-C-04-data-size-accounting.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
