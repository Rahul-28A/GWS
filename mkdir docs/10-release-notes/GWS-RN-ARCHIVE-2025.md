# Archived Release Notes — Google Workspace 2025

**Article ID:** GWS-RN-ARCHIVE-2025  
**Audience:** All

For the latest release notes, see [Release Notes — Druva for Google Workspace](GWS-RN-01-release-notes-current.md).

---

## September 20, 2025

This release contains minor bug fixes.

---

## September 6, 2025

This release contains minor bug fixes.

---

## August 23, 2025

### Enhancement — Expanded character limit for Legal Hold names

The character limit for Legal Hold names has increased from **35 to 150 characters**. This allows more descriptive and precise names — for example, `EmployeeID_EmployeeName_LegalHoldID` — to better match your organization's naming conventions.

---

## August 9, 2025

### Feature — eDiscovery Download Client v2.2.0

An updated version of the eDiscovery Download Client (v2.2.0) is now available.

- [Download eDiscovery Download Client v2.2.0](https://downloads.druva.com/insync/ediscovery/2-2-0/)
- [Upgrade eDiscovery Download Client](https://help.druva.com/en/articles/8513275-upgrade-ediscovery-download-client)

### Known issue added

| Issue ID | Description |
|----------|-------------|
| INS-175692 | When an entire Shared Drive is deleted, attempting to restore individual files from an older snapshot fails with a `File not found` error. **Workaround:** Select the entire Shared Drive for restoration instead of individual files. |

---

## July 26, 2025

This release contains minor bug fixes.

---

## July 12, 2025

### Enhancement — Sensitive Data Governance: Keyword Whitelist and File Violations

- **Whitelist capacity increased 10x** — now supports up to 10,000 entries (previously 999), enabling more precise false-positive reduction.
- **SHA1 checksum integration** — SHA1 checksum values are now visible in the Non-Compliant File Report, searchable on the File Violations page (`Checksum:<SHA1 value>`), and included in file violation details.

See [Non-Compliant File Report](https://help.druva.com/en/articles/9219535-non-compliant-file-report).

---

## June 28, 2025

### Deprecation — Legal Hold API v1 and v2

Druva has deprecated Legal Hold API versions v1 and v2. These versions are no longer accessible.

**Action required:** Migrate to the [Legal Hold API v3 and v4](https://developer.druva.com/reference/get_legalholds-v3-policies).

---

## June 14, 2025

This release contains minor bug fixes.

---

## May 31, 2025

This release contains minor bug fixes.

---

## May 18, 2025

This release contains minor bug fixes.

---

## May 3, 2025

### Feature — eDiscovery Download Client v2.1.0

An updated version of the eDiscovery Download Client (v2.1.0) is now available.

- [Download eDiscovery Download Client v2.1.0](https://downloads.druva.com/insync/ediscovery/2-1-0/)

> **⚠️ Important**  
> Ensure `http://downloads.druva.com/` is whitelisted in your firewall or network security settings before downloading.

---

## April 19, 2025

This release contains minor bug fixes.

### Known issue added

| Issue ID | Description |
|----------|-------------|
| INS-202881 | Large Google Slides or PowerPoint (.PPTX) files > 400 MB stored in Google Drive may fail to download during backup and are skipped. **Workaround:** Split into smaller files or convert to PDF. |

---

## March 22, 2025

This release contains minor bug fixes.

---

## March 8, 2025

This release contains minor bug fixes.

---

## February 22, 2025

This release contains minor bug fixes.

---

## February 8, 2025

### Enhancement — API support for Google Workspace reports

The following Google Workspace reports now support API access:

| Report | API name |
|--------|---------|
| Alert History Report | `googleAlerts` |
| License Usage Report | `googleLicenseUsage` |
| Preserved Users Datasources Report | `googlePreservedUsersDatasources` |
| Google Shared Drive Backup Activity Report | `googleSharedDriveBackupActivity` |
| Google Shared Drive Restore Activity Report | `googleSharedDriveRestoreActivity` |
| Storage Consumption Report | `googleStorageConsumption` |
| Users Count & Status Report | `googleUserCountAndStatus` |
| User Last Backup Status Report | `googleUserLastBackupStatus` |
| User Provisioning Report | `googleUserProvisioning` |
| User Restore Activity Report | `googleUserRestoreActivity` |
| User Workload Report | `googleUserWorkload` |

See [Google Workspace Reports — Overview and Access](../05-monitor/GWS-05-05-reports-overview.md) and the [Druva Developer Portal](https://developer.druva.com/reference/choose-your-druva-product).

---

## January 25, 2025

### Enhancement — Enhanced Restore Options for Calendar

You can now restore **selective calendar events** or **entire calendars** with granular control. This reduces disruption to users when recovering from accidental deletions.

See [Restore Gmail Data — Calendar section](../04-restore/GWS-04-01-restore-gmail.md).

### Fixed issue

| Issue ID | Description |
|----------|-------------|
| REAL-51341 | Fixed: Sensitive Data Violation emails were being sent to all users, including those with no violations. Emails are now sent only to users with one or more violations. |

### Known issues

| Issue ID | Description |
|----------|-------------|
| INS-182239 | When a single event is deleted from a recurring Google Calendar series and an in-place restore is performed for the entire series, the deleted event is not recreated. |
| INS-182780 | Birthday and Task calendars from Google Workspace are not backed up. |

---

## January 11, 2025

### Enhancement — New filter for Legal Hold Policy API

The List Legal Hold Policies v4 API now supports filtering by `legalHoldTypeIds`. See [Legal Hold APIs v4](https://developer.druva.com/reference/policiesget).

### Feature — eDiscovery Download Client v2.0.9

- [Download eDiscovery Download Client v2.0.9](https://downloads.druva.com/insync/ediscovery/2-0-9/)

---

## January 4, 2025

### Enhancement — Refreshed Cyber Resilience user interface

The Cyber Resilience interface has been updated for a more intuitive experience. See [Cyber Resilience release notes](https://help.druva.com/en/articles/10346485-release-notes-cyber-resiliency).

---

## December 28, 2024

This release contains minor bug fixes.

---

## December 14, 2024

This release contains minor bug fixes.

---

## November 30, 2024

This release contains minor bug fixes.

---

## November 16, 2024

### Enhancement — Regular Expression support in Sensitive Data Governance Whitelist

The Whitelist feature now supports **Regular Expression (regex)** patterns in addition to standard keywords. This enables more flexible and accurate whitelisting rules to reduce false positives.

See [Adding Keywords to Whitelist](https://help.druva.com/en/articles/8513234-whitelist-keywords-and-regular-expressions-in-sensitive-data-governance).

---

## November 2, 2024

### Feature — eDiscovery Download Client v2.0.8

- [Download eDiscovery Download Client v2.0.8](https://downloads.druva.com/insync/ediscovery/2-0-8/)

---

## October 19, 2024

This release contains minor bug fixes.

---

## October 5, 2024

This release contains minor bug fixes.
