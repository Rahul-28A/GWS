# Manage Google Directory Mappings and Auto-Preserve

**Article ID:** GWS-02-06  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

After setting up Google Directory provisioning, you can manage the priority order of your mappings, delete mappings you no longer need, and control how Druva handles users who are removed from a mapping.

---

## Before you begin

- You have set up [Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md).
- You have the **Druva Cloud Administrator** role.

---

## How mapping priority works

When a user belongs to multiple mappings, Druva imports the user using the **highest-priority mapping** — that mapping's Profile and storage assignment apply. The mapping at the top of the list has the highest priority. The most recently created mapping has the lowest priority by default.

**Example:** A user is in both the "Engineering" group (mapped to Profile A, US storage) and the "All Users" group (mapped to Profile B, EU storage). If "Engineering" is ranked higher, the user gets Profile A and US storage.

---

## Set mapping priority order

1. Go to **Google Workspace > Users > User Provisioning**.
2. Click the **Mappings** tab.
3. Click the **three-dot menu (⋮)** next to any mapping.
4. Select **Set Mapping Priority Order**.
5. Drag and drop the mappings into your desired priority order (top = highest priority).
6. Click **Save**.

A confirmation message appears: "Successfully updated Mapping priority."

---

## Delete a mapping

Deleting a mapping stops Druva from using it to import new users. Users that were already imported via the deleted mapping remain in Druva, but their behavior changes depending on your auto-preserve setting.

**If auto-preserve is enabled:**
- Users in the deleted mapping who are **not** in any other active mapping are moved to **Preserved** state.
- Users in the deleted mapping who **are** in another active mapping remain Active and continue under the other mapping.

**If auto-preserve is disabled:**
- Users imported via the deleted mapping remain in their current state (Active or Preserved) unchanged.

> **📝 Note**  
> Preserved users' data is retained, but new backups stop. Preserved licenses are consumed for these users.

To delete a mapping:

1. Go to **Google Workspace > Users > User Provisioning**.
2. Click the **Mappings** tab.
3. Select the mapping you want to delete.
4. Click the **three-dot menu (⋮)** and select **Delete Mapping**.
5. On the confirmation dialog, click **Delete Mapping**.

A confirmation message appears: "Google Directory Mapping successfully removed."

> **📝 Note**  
> Auto-preserve logic runs on the **next scheduled auto-sync** after the mapping is deleted. Users are not immediately preserved upon mapping deletion.

---

## Manage users imported via mixed methods

If users were initially imported manually (via CSV or API) and you later switch to Google Directory provisioning:

- Users **found in Google Directory** will be provisioned through it in future syncs.
- Users **not in Google Directory** continue to be provisioned manually.

---

## Related articles

- [Set Up Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md)
- [Change the User Provisioning Method](GWS-02-07-change-provisioning-method.md)
- [Understand License Consumption](../05-monitor/GWS-05-04-license-consumption.md)
