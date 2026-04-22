# Supported Google Workspace Editions and Data Types

**Article ID:** GWS-01-02  
**Audience:** Administrators, IT managers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Use this page as a quick reference for everything Druva inSync supports and excludes when protecting Google Workspace data — editions, data types, metadata fields, and file formats.

---

## Supported Google Workspace editions

| Edition | Supported |
|---------|-----------|
| Business Starter | ✅ Yes |
| Business Standard | ✅ Yes |
| Business Plus | ✅ Yes |
| Enterprise | ✅ Yes |
| Frontline | ❌ Not supported |
| Education (Fundamentals / Standard / Plus) | ❌ Not supported |
| Nonprofits | Contact support to confirm |

---

## Supported workloads

| Workload | What Druva protects |
|----------|-------------------|
| **Gmail** | Emails, attachments, calendar events, contacts |
| **Google Drive** | Files, folders, trash, comments, sharing settings |
| **Shared Drives** | Drive contents, member details, access rights, settings, trash |

---

## Gmail — data and metadata

### Data backed up

| Item | Details |
|------|---------|
| Emails | Full message body and all attachments |
| Calendar events | Event details; attachment links (not the files — stored in Drive) |
| Contacts | All contacts and contact groups |
| Other Contacts | Name, Phone Number, Email Address only (Google People API limitation) |

### Metadata backed up

| Category | Fields |
|----------|--------|
| Email | To, From, Cc, Bcc, Subject, Sent On, Received On |
| Attachment | Name, Size |
| Timestamps | Created, Modified, Received, Sent |
| Organization | Labels |

> **⚠️ Important**  
> Backup and restore of **Other Contacts is not supported on GovCloud**.

---

## Google Drive — data and metadata

### Data backed up

| Item | Details |
|------|---------|
| Files | Owned by the user, or shared with download permission |
| Folders | All folder structures including nested subfolders |
| Trash | Files in the user's trash at backup time |
| Comments | File comments (subject to Google API availability) |

### Metadata backed up

Title, Description, Created Date, Modified Date, File Size, Original Filename, Owners, Last Modifying User, MD5 Checksum

---

## Shared Drives — data backed up

| Category | Details |
|----------|---------|
| Drive identity | Name of each Shared Drive |
| Members | User ID, name, access rights, account creation date, active period |
| Settings | Drive themes, images, configuration |
| Content | Files (supported MIME types), folders, subfolders, folder metadata |
| Sharing settings | Internal and external file sharing settings |
| Trash | Deleted items within the drive |

---

## Supported native Google MIME types

Druva backs up these native Google file formats. All other native Google types are skipped.

| MIME type | Format |
|-----------|--------|
| `application/vnd.google-apps.document` | Google Docs |
| `application/vnd.google-apps.spreadsheet` | Google Sheets |
| `application/vnd.google-apps.presentation` | Google Slides |
| `application/vnd.google-apps.drawing` | Google Drawings |

Non-native files (PDFs, DOCX, XLSX, images, etc.) are backed up in their original format regardless of size (subject to file size limits below).

---

## File size limits

| File type | Limit | Workaround |
|-----------|-------|------------|
| Google Slides / PPTX | > 400 MB may fail | Split into smaller files or convert to PDF |
| Files with long names | > 1,024 characters cannot be backed up | Rename the file with a shorter name |

---

## Exclusions — what is not backed up

| Excluded item | Reason |
|--------------|--------|
| Google Forms | Not supported |
| Google Sites | Not supported |
| My Computer folder | Local sync folder only; not a cloud data source |
| Birthday calendar | Google API limitation |
| Tasks calendar | Google API limitation |
| Archived user data | Google API limitation |
| Google Vault data | Google API limitation |
| Files in Shared Drives with Google API known issues | See [Google's known issues list](https://support.google.com/a/answer/7337638) |

---

## Related articles

- [Google Workspace Backup with Druva — Overview](GWS-01-01-overview.md)
- [Quick-Start Checklist](GWS-01-03-quickstart-checklist.md)
- [Supported MIME Types for Google Workspace Backup](../09-concepts/GWS-C-02-mime-types.md)
- [File Size Limits and Workarounds](../09-concepts/GWS-C-03-file-size-limits.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
