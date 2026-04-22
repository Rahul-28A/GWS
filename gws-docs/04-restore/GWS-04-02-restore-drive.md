# Restore Google Drive Data

**Article ID:** GWS-04-02  
**Audience:** Druva Cloud Administrators, End users (via inSync Web)  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Restore backed-up Google Drive data directly to a user's Google Drive account, to a different user's account, or to a user's device. You can restore a full Drive, individual folders, or specific files.

Administrators restore data using the **Druva Console**. End users can restore their own data using [inSync Web](https://help.druva.com/en/articles/8829657-restore-data-using-the-insync-web).

> **⚠️ Important — Existing customers**  
> To use the native Google Drive restore feature, existing inSync Google Workspace customers must first [reconfigure Google Workspace](../02-setup/GWS-02-03-reconfigure-gws.md) in the Druva Console.

---

## Before you begin

- The user's Google Drive is configured for backup and has at least one snapshot.
- You have the **Druva Cloud Administrator** role.
- For cross-user restores, the destination user must exist in Druva.
- Note: A user's Google Drive backup **cannot** be restored to a Shared Drive, and vice versa.
- Files with identical names **cannot** be restored to devices simultaneously.

---

## Restore Google Drive data

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace > Users**.
2. Click the **username** of the user whose data you want to restore.
3. Click **Restore Data** and select **Google Drive** as the data source.
4. Select the **snapshot** you want to restore from.
5. Browse to find the files or folders you want to restore.  
   Alternatively, use the **search** option to find specific files by name.
6. Click **Restore**.
7. On the **Restore** window, select your options (see [Restore options](#restore-options) below) and click **Restore**.

---

## Restore options

### Restore Location

| Option | What it does |
|--------|-------------|
| **Restore to the same User Account** | Restores to the original user's Google Drive |
| **Restore to a Different User Account** | Restores to another user's Google Drive. Ownership of restored files transfers to the destination user. |
| **Restore to a User's device** | Restores to the user's local device via inSync Client |

When restoring to a different user's account, type the user's name or email in the **Select** field.

### Restore Options

| Option | What it does |
|--------|-------------|
| **Restore as a Copy** (default) | Creates a new `inSync-restore-<date>-<time>` folder in the user's Drive and restores all selected data there |
| **In-Place Restore** | Overwrites existing data in the specified Drive location with the selected snapshot data |

> **📝 Note**  
> - In-Place Restore is only available when restoring to the **same user's account**.
> - Google native Drawings are restored as `.JPEG` image files.
> - If the parent folder of selected files was deleted from Google Drive, the restore fails with a "file not found" type error. Restore the parent folder first, or restore the entire Drive.
> - In-Place Restore fails for files with multiple parent folders if the selected parent folder is missing.

### Retain share settings

Select this checkbox to preserve the original file-sharing settings when restoring. By default, sharing settings are **not** retained during restore. Available only when restoring to the same user's account.

---

## What happens to file and folder names

**Permissions:** All file/folder permissions (write access, share links, etc.) are restored exactly as they were at the time of the backup snapshot.

**Renamed duplicates:** If Druva renamed a file or folder during backup (because two files had the same name), the file is restored with its **original name** in Google Drive. For example, a file backed up as `Report.txt-0180J7` is restored as `Report.txt`.

**Shared folder naming conflicts:** If a personal folder and a Shared folder have the same name, Druva renamed the Shared folder as `<name> <internal ID>` during backup. On restore, only the personal folder name is preserved.

---

## Related articles

- [Restore Gmail Data](GWS-04-01-restore-gmail.md)
- [Restore Shared Drives Data](GWS-04-03-restore-shared-drives.md)
- [Download Google Workspace Data](GWS-04-04-download-gws-data.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
