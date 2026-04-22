# Enable eDiscovery and Legal Hold for Google Workspace

**Article ID:** GWS-07-01  
**Audience:** Druva Cloud Administrators, Compliance officers, Legal teams  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

eDiscovery in Druva lets you place **legal holds** on Google Workspace data to prevent it from being deleted — even if the normal retention period expires. This is essential during litigation, regulatory investigations, or compliance audits. Once data is under legal hold, you can access it via WebDAV for review and export.

---

## Before you begin

- You have the **Druva Cloud Administrator** role.
- The relevant users' Gmail and Google Drive data is already being backed up.
- Confirm your license includes eDiscovery / Data Governance capabilities.

---

## How legal hold works in Druva

When a legal hold policy is applied to a user:

- Druva **preserves** all backed-up data for that user, regardless of the normal retention policy.
- Data is **not deleted** even when retention periods would normally expire.
- The administrator can access preserved data through WebDAV for review and download.
- Legal hold does **not** trigger new backups — it only preserves already-backed-up data.

The **Data by Source** area on the **Data Governance** page shows how preserved data is distributed across users and data sources.

---

## Step 1 — Create or update a legal hold policy

A legal hold policy defines which users' data to preserve and for how long.

1. Sign in to the **Druva Cloud Platform Console**.
2. Navigate to **Data Governance > Legal Hold**.
3. Click **Create Legal Hold Policy** (or edit an existing policy).
4. Define the policy settings:
   - **Policy name** — use a descriptive name that identifies the case or matter (up to 150 characters).
   - **Custodians** — select the users whose data should be preserved.
   - **Data sources** — select Gmail and/or Google Drive.
5. Save the policy.

For complete instructions, see [Create a Legal Hold Policy](https://help.druva.com/en/articles/8513261-create-a-legal-hold-policy).

---

## Step 2 — Access legal hold data via WebDAV

After applying the legal hold policy, access the preserved data using a WebDAV client for review and export.

See [Access Legal Hold Data via WebDAV](GWS-07-02-webdav-access.md) for full instructions.

---

## Step 3 — Monitor eDiscovery data

Track which users are under legal hold and the distribution of preserved data:

1. Navigate to **Data Governance** in the Druva Console.
2. Review the **Data by Source** section to see data distribution across users and data sources under hold.

---

## Important behaviors and limitations

| Item | Behavior |
|------|---------|
| **Legal hold vs. retention** | Legal hold overrides retention — data is never deleted while hold is active |
| **New backups** | Legal hold does not trigger backups; only preserves existing snapshots |
| **Multiple attachments** | If a Gmail message has multiple attachments, inSync creates one `.eml` file for the email and separate `.eml` files for each attachment. All are accessible via WebDAV. |
| **Legal Hold icon in dashboard** | Users under legal hold display a ⚖️ icon in the Gmail and Google Drive tabs |

---

## eDiscovery Download Client

For large-scale legal hold data exports, use the **eDiscovery Download Client** — a desktop application that downloads legal hold data in bulk. The current version is **v2.3.0**.

- [Download eDiscovery Download Client v2.3.0](https://downloads.druva.com/insync/ediscovery/2-3-0/)
- [Upgrade eDiscovery Download Client](https://help.druva.com/en/articles/8513275-upgrade-ediscovery-download-client)
- [Support Matrix for eDiscovery Download Client](https://help.druva.com/en/articles/8513270-support-matrix-for-ediscovery-download-client)

> **⚠️ Important**  
> Upgrade to the latest eDiscovery Download Client only after all active download jobs on older client versions have finished.

---

## Related articles

- [Access Legal Hold Data via WebDAV](GWS-07-02-webdav-access.md)
- [Retrieve Google Drive Metadata Attributes via WebDAV](GWS-07-03-metadata-webdav.md)
- [Create a Legal Hold Policy](https://help.druva.com/en/articles/8513261-create-a-legal-hold-policy)
- [Rollback Deleted Devices and Snapshots](../06-manage/GWS-06-04-rollback.md)
