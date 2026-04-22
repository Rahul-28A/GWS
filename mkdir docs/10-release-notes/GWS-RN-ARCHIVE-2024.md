# Archived Release Notes — Google Workspace 2024

**Article ID:** GWS-RN-ARCHIVE-2024  
**Audience:** All

For the latest release notes, see [Release Notes — Druva for Google Workspace](GWS-RN-01-release-notes-current.md).

---

## September 21, 2024

This release contains minor bug fixes.

---

## September 7, 2024

This release contains minor bug fixes.

---

## August 24, 2024

This release contains minor bug fixes.

---

## August 10, 2024

### Feature — eDiscovery Download Client v2.0.7

An updated version of the eDiscovery Download Client (v2.0.7) is now available.

- [Download eDiscovery Download Client v2.0.7](https://downloads.druva.com/insync/ediscovery/2-0-7/)

### Feature — Administrator Management with AD/LDAP (General Availability)

Administrator management using AD/LDAP is now generally available. This feature allows Druva Cloud Platform (DCP) administrators to manage Druva administrators using your existing AD/LDAP integration.

**Key changes:**
- A new version of the AD/LDAP Connector is required to support this feature.
- AD/LDAP Connector and Account settings have moved from "End Points and SaaS Apps Settings" to the **Druva Cloud Settings** section in the DCP Console.
- Upgrading AD/LDAP Connectors is now an exclusive privilege of Druva Cloud Administrators.

**Action required:** Upgrade all existing AD/LDAP Connectors to grant inSync and DCP administrators permission to modify mappings and configurations.

See [Upgrade AD/LDAP Connectors](https://help.druva.com/en/articles/9240357-upgrade-ad-ldap-connectors-for-existing-insync-customers).

---

## July 27, 2024

This release contains minor bug fixes.

---

## July 13, 2024

### Fixed issue

| Issue ID | Description |
|----------|-------------|
| REAL-42263 | **Data Governance:** Enhanced Data Governance Reports now correctly show data for deleted users and devices, and for users removed from Legal Hold. |

---

## June 29, 2024

### Feature — Enhanced eDiscovery reports: Non-Compliant Files and Defensible Delete for Emails

Centralized reporting for **Non-Compliant Files** and **Defensible Delete for Emails** reports is now available on the Druva Cloud Platform Console.

**Benefits:**
- Advanced filtering and sorting.
- Simplified report subscription management.
- Graphs and charts for easier data interpretation.

See [Non-Compliant File Report](https://help.druva.com/en/articles/9219535-non-compliant-file-report) and [Defensible Delete for Emails Report](https://help.druva.com/en/articles/9219554-defensible-delete-for-emails-report).

### Enhancement — Last Sync Time added to User Provisioning tab

The **User Provisioning** tab now shows **Last Sync Time** — the timestamp of the most recent successful synchronization with your Google Directory.

### Enhancement — Mapping column added to User Provisioning Report

The User Provisioning Report for Microsoft 365 and Google Workspace now includes a **Mapping** column showing the highest-priority mapping used to import each user. See [User Provisioning Report](https://help.druva.com/en/articles/9250602-user-provisioning-report).

---

## June 15, 2024

This release contains minor bug fixes.

---

## June 1, 2024

### Feature — Google Workspace centralized reports on Druva Cloud Platform

Centralized reporting for Google Workspace is now available on the DCP Console. Reports available in this release:

- User Workload Report
- User Last Backup Status Report
- User Restore Activity Report
- Users Count & Status Report
- License Usage Report
- Alert Report
- Storage Consumption Report
- User Provisioning Report
- Preserved Users Datasources Report
- Google Shared Drive Backup Activity Report
- Google Shared Drive Restore Activity Report

See [About Reports](https://help.druva.com/en/articles/9250632-about-reports-in-google-workspace) and [Google Workspace Reports — Overview and Access](../05-monitor/GWS-05-05-reports-overview.md).

### Feature — Enhanced eDiscovery reports: Global Custodian and eDiscovery Download Jobs

Centralized reporting for **Global Custodian** and **eDiscovery Download Jobs** is now available on the DCP Console.

See [Global Custodian Report](https://help.druva.com/en/articles/9373652-global-custodian-report) and [eDiscovery Download Jobs Report](https://help.druva.com/en/articles/9373664-ediscovery-download-jobs-report).

---

## May 18, 2024

### Enhancement — New parameters for file violations list APIs

The file violations list APIs now include the following additional fields:

File Name, Policy Violation (Name), Sensitive Data Found, UserName, Datasource, Violation Reported On, Resolved On, Resolution Details, Additional Comment.

See [Get File Violations API](https://developer.druva.com/reference/get_sdg-v1-fileviolations).

---

## May 4, 2024

### Enhancement — Archived Non-Compliant and Defensible Delete For Files reports migrated

These reports are now available on the centralized reporting platform:

- [Archived Non-Compliant Files Report](https://help.druva.com/en/articles/9219545-archived-non-compliant-file-report)
- [Defensible Delete For Files Report](https://help.druva.com/en/articles/9219551-defensible-delete-for-files-report)

### Feature — eDiscovery Download Client v2.0.6

- [Download eDiscovery Download Client v2.0.6](https://downloads.druva.com/insync/ediscovery/2-0-6/)

---

## April 27, 2024

### Feature — Administrator Management with AD/LDAP (Preview)

This release introduced Administrator Management functionality using your existing AD/LDAP integration.

> **⚠️ Note:** General availability was released on August 10, 2024. Contact your Druva Account Manager to enable this feature.

---

## April 20, 2024

### Feature — Enterprise Key Management for Google Workspace

You can now use keys generated from your **AWS Key Management Service (KMS)** account to encrypt and decrypt data backed up by Druva inSync. This adds an additional encryption layer beyond Druva's default backup encryption.

**Key benefits:**
- Use your own AWS KMS keys to protect backups.
- Full ownership of the encryption and decryption key — revoke at any time.
- Druva does not store your key.

**Action required:** Enterprise Key Management is available on request. Contact Druva Support to enable it for your account.

See [Enterprise Key Management for Druva Cloud Protection](https://help.druva.com/en/articles/8702841-enterprise-key-management-for-endpoints-saas-apps).

---

## April 6, 2024

### Announcement — New Help Center address

Druva's documentation has moved from `docs.druva.com` to **help.druva.com**. All existing URLs redirect automatically.

**Action required:** Update any saved bookmarks to use `help.druva.com`.

---

## March 23, 2024

### Feature — Google Directory Integration for User Provisioning (General Availability)

Google Directory is now available as a user provisioning method alongside Azure AD, AD/LDAP, and SCIM.

**Benefits:**
- Import users from Google Workspace by Google Group or all users.
- Create and prioritize user mappings for granular control.
- Auto-sync and on-demand sync to keep user data current.

**Action required:**
- **Existing customers:** Reconfigure the Google Workspace app to use Google Directory. See [Reconfigure Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md).
- **New customers:** Select Google Directory as your provisioning method during initial setup.

See [Set Up Google Directory User Provisioning](../02-setup/GWS-02-05-google-directory-provisioning.md).

### Feature — eDiscovery Download Client v2.0.5

- [Download eDiscovery Download Client v2.0.5](https://downloads.druva.com/insync/ediscovery/2-0-5/)

---

## March 9, 2024

This release contains minor bug fixes.

---

## February 10, 2024

This release contains minor bug fixes.

---

## January 27, 2024

This release contains minor bug fixes.
