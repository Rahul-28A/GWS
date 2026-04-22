# Restore Shared Drives Data

**Article ID:** GWS-04-03  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Restore backed-up Shared Drives data from any available snapshot — either as an in-place overwrite or as a copy to a new Shared Drive. You can restore the entire drive, specific folders, or individual files.

---

## Before you begin

- The Shared Drive has at least one backup snapshot available.
- You have the **Druva Cloud Administrator** role.
- Note: A Shared Drive backup **cannot** be restored to a personal Google Drive, and vice versa.
- Quarantined snapshots (marked with a 🔒 icon) **cannot** be used for restore or download.

---

## Restore Shared Drives data

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace > Shared Drives**.
2. Click the name of the Shared Drive you want to restore.
3. Click the **Backups** tab to see available snapshots.

> **📝 Note — Snapshot icons**  
> - 🔒 **Padlock icon** — snapshot is quarantined (blocked by ransomware detection); cannot be restored.  
> - ❗ **Exclamation icon** — latest clean snapshot; this snapshot cannot be deleted.

4. Select the snapshot you want to restore from, then click **Restore**.  
   The **Restore Data** window appears.
5. Browse and select the **folders and files** you want to restore, or use **Search Files** (top of the window) to find specific files by name or SHA1 hash.

### Search filters (optional)

| Filter | Use for |
|--------|---------|
| File Extensions | Narrow by file type |
| File Size | Filter by size range |
| Modified between | Filter by modification date range |

6. Click **Restore**.
7. On the **Restore** window, select a restore option:

| Option | What it does |
|--------|-------------|
| **In-place Restore** | Overwrites existing data in the Shared Drive with the selected snapshot data |
| **Restore as a Copy** | Creates a new Shared Drive named `inSync-restore-<date>-<time>` under Shared Drives and restores data there |

8. Click **OK** to confirm.

---

## Restore limitations for Shared Drives

| Limitation | Detail |
|-----------|--------|
| Themes and Images | Cannot be restored due to an internal API error |
| Large folder trees | Some subfolders may not appear in the UI folder tree when navigating drives with many folders. This is a display issue only — all items are still restored correctly. |
| Individual files from deleted drives | If an entire Shared Drive was deleted and you try to restore individual files from an older snapshot, the restore fails with a `File not found` error. Select the entire Shared Drive for restoration instead. |

---

## Download Shared Drives data instead of restoring

If you need to download files from a Shared Drive snapshot (rather than restore them to Google):

1. Follow steps 1–4 above.
2. Select the files and folders you want to download.
3. Click **Download** instead of **Restore**.  
   Files download to your browser's default download location. Folders download as `<folder name>.zip`.

---

## Related articles

- [Restore Google Drive Data](GWS-04-02-restore-drive.md)
- [Download Google Workspace Data](GWS-04-04-download-gws-data.md)
- [Manage and Delete Shared Drives](../06-manage/GWS-06-02-manage-shared-drives.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
- [Ransomware Recovery for Google Workspace](https://help.druva.com/en/articles/8513175-ransomware-recovery-for-google-workspace)
