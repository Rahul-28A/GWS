# Retrieve Google Drive Metadata Attributes via WebDAV

**Article ID:** GWS-07-03  
**Audience:** Druva Cloud Administrators, developers, compliance teams  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva backs up standard Google Drive metadata (Title, Description, Created Date, Modified Date, File Size, Owners, MD5 Checksum, etc.) for all protected files. If you need to retrieve **additional or extended** Google Drive metadata attributes through WebDAV, configure your WebDAV client with a specific property request.

---

## Standard metadata captured by Druva

The following metadata fields are captured automatically for every backed-up Google Drive file:

| Field | Description |
|-------|-------------|
| Title | File or folder name |
| Description | File description (if set) |
| Created Date | When the file was created |
| Modified Date | When the file was last modified |
| File Size | Size of the file in bytes |
| Original Filename | The filename at the time of backup |
| Owners | Google account(s) that own the file |
| Last Modifying User | The user who last edited the file |
| MD5 Checksum | Hash for file integrity verification |

---

## Retrieve extended Google Drive metadata via WebDAV

To retrieve all available Google Drive metadata attributes (beyond the standard set above), add one of the following settings to your WebDAV client configuration:

```
properties = [getgdriveproperties]
```

or

```
include = [getgdriveproperties]
```

Once configured, Druva returns the full set of Google Drive metadata attributes available from the Google Drive API.

For the complete list of available attributes, see the [Google Drive API Files reference](https://developers.google.com/drive/v2/reference/files).

---

## When to use this

Use extended metadata retrieval when:

- Your eDiscovery workflow requires metadata fields beyond the standard set (for example, `viewedByMeDate`, `sharingUser`, or custom properties).
- You are integrating Druva WebDAV output with an eDiscovery platform that ingests structured metadata.
- You need to verify sharing history or access records for compliance purposes.

---

## Related articles

- [Enable eDiscovery and Legal Hold for Google Workspace](GWS-07-01-ediscovery-legal-hold.md)
- [Access Legal Hold Data via WebDAV](GWS-07-02-webdav-access.md)
