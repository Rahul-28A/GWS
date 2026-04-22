# Access Legal Hold Data via WebDAV

**Article ID:** GWS-07-02  
**Audience:** Druva Cloud Administrators, Compliance officers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

After applying a legal hold policy to Google Workspace users, access their preserved data using a **WebDAV client**. WebDAV provides read-only access to backed-up Gmail and Google Drive data for review, export, and eDiscovery workflows.

---

## Before you begin

- A [legal hold policy](GWS-07-01-ediscovery-legal-hold.md) has been created and applied to the relevant users.
- You have a WebDAV-compatible client installed (for example, Cyberduck, WinSCP, or Finder on macOS).
- You have the **Druva Cloud Administrator** role.

---

## Connect to legal hold data via WebDAV

1. Open your WebDAV client.
2. Connect to the Druva WebDAV endpoint. Use the credentials and server URL provided in your Druva account settings.  
   Refer to [Access Legal Hold Data using WebDAV](https://help.druva.com/en/articles/8513262-access-legal-hold-data-using-webdav) for the exact server URL and authentication steps.
3. Navigate to the user whose data you want to review.
4. Browse the directory structure to access Gmail (`.eml` files) and Google Drive files.

---

## How Gmail data is organized in WebDAV

When Druva backs up a Gmail message with multiple attachments, it stores them as:

- One `.eml` file for the email body.
- Separate `.eml` files for each attachment.

All files are accessible through the WebDAV directory for that user.

---

## Related articles

- [Enable eDiscovery and Legal Hold for Google Workspace](GWS-07-01-ediscovery-legal-hold.md)
- [Retrieve Google Drive Metadata Attributes via WebDAV](GWS-07-03-metadata-webdav.md)
- [Access Legal Hold Data using WebDAV](https://help.druva.com/en/articles/8513262-access-legal-hold-data-using-webdav)
