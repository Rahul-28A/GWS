# Release Notes — Druva for Google Workspace

**Article ID:** GWS-RN-01  
**Audience:** All

> **📝 Note — Staged rollout**  
> Druva Cloud services are updated in stages. If you do not see a listed update yet, it will be available in your region soon. See [Druva Cloud Upgrade Process](https://help.druva.com/en/articles/8580819-druva-cloud-upgrade-process) for details.

For GovCloud release notes, see [GovCloud Release Notes — Google Workspace](GWS-RN-GOVCLOUD.md).  
For older releases, see [Archived Release Notes — 2025](GWS-RN-ARCHIVE-2025.md) and [Archived Release Notes — 2024](GWS-RN-ARCHIVE-2024.md).

---

## April 18, 2026

This release contains minor bug fixes.

---

## April 4, 2026

This release contains minor bug fixes.

---

## March 21, 2026

This release contains minor bug fixes.

---

## March 14, 2026

### Deprecation — Legacy Google Workspace Reports end of life

All legacy reports within the Druva Google Workspace Console have been deprecated and replaced by the **Centralized Reporting** capabilities at the Druva Cloud Platform (DCP) level.

**What changed:** Legacy reports are no longer available in the Google Workspace Console.

**What to use instead:** Navigate to **Left navigation menu > Reports** in the Druva Cloud Platform Console. Centralized reports provide enhanced visibility, improved data accuracy, and a unified reporting experience across all workloads.

**Action required:** [Subscribe to Centralized Platform Reporting](https://help.druva.com/en/articles/12107637-manage-reports).

For the full list of available reports and API access, see [Google Workspace Reports — Overview and Access](../05-monitor/GWS-05-05-reports-overview.md).

---

## March 7, 2026

This release contains minor bug fixes.

---

## February 21, 2026

This release contains minor bug fixes.

---

## February 7, 2026

This release contains minor bug fixes.

---

## January 24, 2026

### Enhancement — API credentials with Read-Only access

You can now create **API credentials** with the **Cloud Admin Read Only** role directly from the Druva Cloud Platform Console. This role is available for API credentials only — it is not available for regular administrator accounts.

**Why this matters:** Organizations integrating Druva with third-party tools can now grant read-only API access, preventing accidental or unauthorized changes while still enabling data visibility.

**How to use it:** See [Create and Manage API Credentials](https://help.druva.com/en/articles/8580838-create-and-manage-api-credentials).

### Enhancement — Refreshed Audit Trails user interface

The Audit Trails UI has been redesigned for improved readability and navigation:

- Updated console font for a cleaner look.
- Administrator and User audit trails are now in separate, clearly labelled sections.

---

## January 18, 2026

### Enhancement — Real-time AD/LDAP sync status and alerts

You can now monitor the status of AD/LDAP synchronization jobs in real time directly from the management console.

**New features:**

- **Last Sync Status** — displays the current sync state based on the configured auto-sync interval.
- **New alert: AD Account Not Reachable** — triggered when the configured AD/LDAP host is unreachable due to network or server issues.
- **New alert: Invalid AD Mapping** — triggered when the configured AD mapping is invalid or the destination OU/group cannot be found.

**Action required:** None. See [Configure Alerts](https://help.druva.com/en/articles/8702858-configure-alert-settings) for alert configuration.

---

## January 10, 2026

### Enhancement — SaaS Apps Status alert severity restored to Critical

The SaaS Apps Status alert severity has been restored from **High** back to **Critical**. When severity was set to High, disconnection alerts were grouped into a single digest email. With Critical severity, administrators now receive an **immediate individual notification** whenever a Google Workspace app is disconnected.

### Enhancement — Refreshed inSync Web user interface

The inSync Web interface has been updated with:

- A new font for improved readability.
- Redesigned workload icons for improved clarity and visual appeal.

See [About the inSync Web interface](https://help.druva.com/en/articles/8829627-about-the-insync-web-interface).

---

## January 3, 2026

### Enhancement — Get backup inactivity alert settings via API

The [List all profiles](https://developer.druva.com/reference/get_profilemanagement-v1-profiles) API now includes the `notifyNoSync` response field, which returns the backup inactivity period configured for each Profile.

---

## December 27, 2025

This release contains minor bug fixes.

---

## December 13, 2025

This release contains minor bug fixes.

---

## December 6, 2025

### Enhancement — Suppress activation emails during API-based user creation

When creating users via the [Create new User API](https://developer.druva.com/reference/post_usermanagement-v1-users), you can now use the `sendPasswordByEmail` field to prevent activation notification emails from being sent. This gives administrators full control over the notification experience during automated user provisioning.

---

## November 29, 2025

### Feature — eDiscovery Download Client v2.3.0

An updated version of the eDiscovery Download Client (v2.3.0) is now available. This release improves the underlying build environment, strengthens cryptographic foundations, and ensures robust secure communication.

- [Download eDiscovery Download Client v2.3.0](https://downloads.druva.com/insync/ediscovery/2-3-0/)
- [Upgrade eDiscovery Download Client](https://help.druva.com/en/articles/8513275-upgrade-ediscovery-download-client)
- [Support Matrix for eDiscovery Download Client](https://help.druva.com/en/articles/8513270-support-matrix-for-ediscovery-download-client)

> **⚠️ Important**  
> Upgrade to v2.3.0 only after all active download jobs on older client versions have completed.

---

## November 15, 2025

### Enhancement — Restore Status alert now includes user details

The Restore Status alert notification now includes three additional fields: **Source User**, **Destination**, and **Initiator**. These fields make it easy to identify all users involved in a restore operation at a glance.

See [Endpoints & SaaS Apps Alerts](https://help.druva.com/en/articles/8702855-endpoints-saas-apps-alerts).

---

## November 1, 2025

This release contains minor bug fixes.

---

## October 18, 2025

This release contains minor bug fixes.

---

## October 4, 2025

This release contains minor bug fixes.

---

## Earlier release notes

- [Archived Release Notes — Google Workspace 2025](GWS-RN-ARCHIVE-2025.md)
- [Archived Release Notes — Google Workspace 2024](GWS-RN-ARCHIVE-2024.md)
- [GovCloud Release Notes — Google Workspace](GWS-RN-GOVCLOUD.md)
