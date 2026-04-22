# GovCloud Release Notes — Google Workspace

**Article ID:** GWS-RN-GOVCLOUD  
**Audience:** GovCloud customers

For public cloud release notes, see [Release Notes — Druva for Google Workspace](GWS-RN-01-release-notes-current.md).

---

## June 28, 2025

### Feature — eDiscovery Download Client v2.1.0 and v2.0.9

Two updated eDiscovery Download Client versions are now available for GovCloud.

**v2.1.0** (recommended):

- [Download eDiscovery Download Client v2.1.0](https://downloads.druva.com/insync/ediscovery/2-1-0/)

> **⚠️ Important**  
> To access v2.1.0, ensure `http://downloads.druva.com/` is whitelisted in your firewall or network security settings.

**v2.0.9** (if v2.1.0 is not yet available in your environment):

- [Download eDiscovery Download Client v2.0.9](https://downloads.druva.com/insync/ediscovery/2-0-9/)

See also:
- [Upgrade eDiscovery Download Client](https://help.druva.com/en/articles/8513275-upgrade-ediscovery-download-client)
- [Support Matrix for eDiscovery Download Client](https://help.druva.com/en/articles/8513270-support-matrix-for-ediscovery-download-client)

### Known issues

| Issue ID | Description |
|----------|-------------|
| INS-202881 | Large Google Slides or PowerPoint (.PPTX) files > 400 MB stored in Google Drive may fail to download during backup and are skipped. **Workaround:** Split into smaller files or convert to PDF. |
| INS-182239 | When a single event is deleted from a recurring Google Calendar series and an in-place restore is performed for the entire series, the deleted event is not recreated. |
| INS-182780 | Birthday and Task calendars from Google Workspace are not backed up. |

### Fixed issue

| Issue ID | Description |
|----------|-------------|
| REAL-51341 | Fixed: Sensitive Data Violation emails were being sent to all users, including those with no violations. Emails are now sent only to users with one or more violations. |

---

## March 22, 2025

### Feature — Enhanced Restore Options for Calendar

GovCloud now supports granular calendar restore — restore selective events or entire calendars with full control.

See [Restore Gmail Data — Calendar section](../04-restore/GWS-04-01-restore-gmail.md).

### Enhancement — New filter for Legal Hold Policy API

The List Legal Hold Policies v4 API now supports filtering by `legalHoldTypeIds`. See [Legal Hold APIs v4](https://developer.druva.com/reference/policiesget).

### Enhancement — Regular Expression support in Sensitive Data Governance Whitelist

The Whitelist feature now supports **Regular Expression (regex)** patterns in addition to standard keywords. See [Adding Keywords to Whitelist](https://help.druva.com/en/articles/8513234-whitelist-keywords-and-regular-expressions-in-sensitive-data-governance).

### Enhancement — User-level download controls for SaaS applications

User-level downloads from the User Portal can now be globally restricted. When enabled, the download option is disabled for end users across all formats (Archive and MDS).

> **📝 Note**  
> This feature requires both an Endpoints license and either a Microsoft 365 or Google Workspace license.

See [Download data using the inSync Web](https://help.druva.com/en/articles/8829660-download-data-using-the-insync-web).

---

## October 19, 2024

### Feature — Enterprise Key Management for Google Workspace

GovCloud now supports Enterprise Key Management using AWS KMS. Use your own AWS KMS keys to encrypt and decrypt backed-up data.

**Key benefits:**
- Use AWS KMS-generated keys to protect Druva inSync backups.
- Full ownership of encryption key — revoke at any time.
- Druva does not store the key.

**Action required:** Enterprise Key Management is available on request. Contact Druva Support.

See [Enterprise Key Management for Druva Cloud Protection](https://help.druva.com/en/articles/8702841-enterprise-key-management-for-endpoints-saas-apps).

---

## Related articles

- [Release Notes — Druva for Google Workspace (Public Cloud)](GWS-RN-01-release-notes-current.md)
- [Archived Release Notes — 2025](GWS-RN-ARCHIVE-2025.md)
- [Archived Release Notes — 2024](GWS-RN-ARCHIVE-2024.md)
- [Enable eDiscovery and Legal Hold for Google Workspace](../07-compliance/GWS-07-01-ediscovery-legal-hold.md)
