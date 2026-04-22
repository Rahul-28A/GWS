# Understand License Consumption

**Article ID:** GWS-05-04  
**Audience:** Druva Cloud Administrators, IT managers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva tracks two types of Google Workspace licenses: **Active** and **Preserved**. Understanding the difference helps you manage costs, plan capacity, and avoid unexpected license overages.

---

## License types

| License type | Who consumes it | When it applies |
|-------------|----------------|----------------|
| **Active** | Current, active users with backup enabled | A user is imported into Druva and their backup is enabled |
| **Preserved** | Users who are no longer active but whose data is still retained | A user is suspended, archived, or removed from Google Directory, and their data is kept per retention policy |

---

## Where to view license consumption

License data appears on the **Google Workspace Overview Dashboard** in the **License card**. Statistics refresh every **7–10 minutes**.

Go to: **Druva Console > Google Workspace > Overview > License card**

---

## What each admin role can see

| Administrator role | Visible data |
|-------------------|-------------|
| **Cloud Administrator** | Total allocated and consumed counts for both Active and Preserved licenses, across all workloads and profiles |
| **Non-Cloud Admin with Manage User permission** | Consumed counts for their assigned workloads and profiles |
| **Non-Cloud Admin without Manage User permission** | Active license consumption only, for their assigned workloads and profiles |

---

## How preserved licenses work

When a user is moved to Preserved status, their data is retained in Druva storage but no new backups run. A Preserved license is consumed until:

- The user is reactivated (moves back to Active status), or
- The user and their data are permanently deleted from Druva.

Users are automatically moved to Preserved status when:

- They are removed from all mapped Google Directory groups (if auto-preserve is enabled).
- They are suspended or archived in Google Directory.

See [Manage Google Directory Mappings](../02-setup/GWS-02-06-manage-directory-mappings.md) for details on auto-preserve configuration.

---

## Reduce license consumption

To reduce the number of Active licenses consumed:

- **Disable** users who no longer need backup (data is retained but the user is no longer Active).
- **Delete** users whose data no longer needs to be retained (data is permanently removed after the rollback window).
- Review the **Backup Data Distribution by Profiles** chart to identify profiles with unexpectedly high user counts.

For license report details, see [Google Workspace Reports — Overview and Access](GWS-05-05-reports-overview.md).

---

## Related articles

- [Navigate the Google Workspace Overview Dashboard](GWS-05-01-overview-dashboard.md)
- [Manage Google Directory Mappings and Auto-Preserve](../02-setup/GWS-02-06-manage-directory-mappings.md)
- [Google Workspace Reports — Overview and Access](GWS-05-05-reports-overview.md)
- [Enable, Disable, or Delete Gmail and Google Drive Data](../06-manage/GWS-06-01-enable-disable-delete-gmail-drive.md)
