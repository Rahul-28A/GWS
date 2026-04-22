# Supported MIME Types for Google Workspace Backup

**Article ID:** GWS-C-02  
**Audience:** All  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva backs up most file types stored in Google Drive — including PDFs, Office documents, images, and other non-native formats — as-is. For **native Google file formats** (files created inside Google Workspace apps), only the types listed below are backed up. All other native Google types are skipped.

---

## Supported native Google MIME types

| MIME type | Native file format |
|-----------|-------------------|
| `application/vnd.google-apps.document` | Google Docs |
| `application/vnd.google-apps.spreadsheet` | Google Sheets |
| `application/vnd.google-apps.presentation` | Google Slides |
| `application/vnd.google-apps.drawing` | Google Drawings |

---

## Unsupported native Google MIME types (always skipped)

| File type | MIME type |
|-----------|-----------|
| Google Forms | `application/vnd.google-apps.form` |
| Google Sites | `application/vnd.google-apps.site` |
| Google Maps | `application/vnd.google-apps.map` |
| Google Jamboard | `application/vnd.google-apps.jam` |
| Google Apps Script | `application/vnd.google-apps.script` |
| Shortcut files | `application/vnd.google-apps.shortcut` |

---

## Non-native files

All non-native files (PDFs, Microsoft Office files, images, videos, ZIP archives, etc.) stored in Google Drive are backed up in their original format, regardless of the file extension — subject to [file size limits](GWS-C-03-file-size-limits.md).

---

## Related articles

- [Google Workspace Backup with Druva — Overview](../01-getting-started/GWS-01-01-overview.md)
- [Supported Google Workspace Editions and Data Types](../01-getting-started/GWS-01-02-supported-editions-data-types.md)
- [File Size Limits and Workarounds](GWS-C-03-file-size-limits.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
