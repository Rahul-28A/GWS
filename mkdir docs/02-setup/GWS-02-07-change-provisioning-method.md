# Change the User Provisioning Method

**Article ID:** GWS-02-07  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

You can switch between user provisioning methods without losing any backed-up data. This is useful when your organization migrates from one identity management system to another — for example, from AD/LDAP to Google Directory.

---

## Supported provisioning methods

You can switch between any of these methods:

- Google Directory
- Azure AD
- SCIM
- AD/LDAP

---

## What happens when you switch

> **⚠️ Important — Read before switching**  
> Switching provisioning methods has the following effects:
> - All **mappings** and **settings** from the previous method are **deleted**.
> - All users provisioned by the previous method are moved to **Manual** provisioning mode.
> - Backed-up data for these users is **not affected** — no data is lost.
> - Users will continue to have their backup data accessible, but future provisioning changes (such as auto-preserve on deletion) will need to be managed manually until you set up new mappings.

---

## Change the provisioning method

1. Go to **Google Workspace > Users**.
2. Click the **User Provisioning** tab.
3. In the **Summary** section, click the **three-dot menu (⋮)**.
4. Select **Change User Deployment Method**.
5. Select the new provisioning method from the options.
6. Click **Save**.
7. On the confirmation dialog, click **Confirm**.

A confirmation message appears: "User provisioning method updated successfully."

---

## What to do after switching

After switching, set up your new provisioning method:

| New method | Next step |
|-----------|-----------|
| Google Directory | [Set Up Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md) |
| AD/LDAP | Configure your AD/LDAP connector and create mappings |
| Azure AD | Configure the Azure AD integration |
| SCIM | Configure SCIM provisioning in your identity provider |

---

## Related articles

- [Set Up Google Directory User Provisioning](GWS-02-05-google-directory-provisioning.md)
- [Manage Google Directory Mappings](GWS-02-06-manage-directory-mappings.md)
- [User Mapping Logic](../09-concepts/GWS-C-05-user-mapping-logic.md)
