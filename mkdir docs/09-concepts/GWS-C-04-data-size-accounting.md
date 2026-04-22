# Why Does Druva Show More Data Than Google Storage?

**Article ID:** GWS-C-04  
**Audience:** All  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

If you compare backup data size in Druva with storage usage in Google, you will almost always see a higher number in Druva. This is expected and not a sign of a problem. This article explains why the two numbers differ.

---

## Summary

Druva and Google count storage differently. In every case below, Druva's count is **higher** than Google's — by design.

---

## Reason 1 — Native Google files

**Google Storage:** Does not count the size of native files (Google Docs, Sheets, Slides, Drawings).

**Druva:** Counts the actual exported size of native files when they are backed up.

**Impact:** Even if a user has only native Google files, Druva will show a non-zero backup size while Google shows zero storage consumed for those files.

---

## Reason 2 — Deleted files are retained in Druva

**Google Storage:** As soon as a file is permanently deleted (emptied from Trash), Google stops counting it toward storage.

**Druva:** Keeps the file in its backup snapshots until the retention period for those snapshots expires. The file continues to count toward Druva backup size until it is compacted out of all snapshots.

**Impact:** If users frequently delete files, the gap between Druva and Google storage counts grows proportionally.

---

## Reason 3 — Files in multiple locations

**Google Storage:** A file shared to or placed in multiple folders in Google Drive is counted **once**.

**Druva:** Counts **each copy** of the same file in each folder separately.

**Impact:** A 5 MB file stored in three different folders in Google Drive counts as 5 MB in Google but 15 MB in Druva.

---

## Reason 4 — Actual file size vs. compressed size

**Google Storage:** Google stores files in a compressed format and reports compressed size.

**Druva:** Reports the **actual (uncompressed) file size** as provided by the Google API when the file is read for backup.

**Impact:** Druva's reported sizes are based on the real content size, not Google's compressed representation.

---

## How to reduce the gap

You can reduce duplicate counting by excluding shared data owned by other users:

1. In the Druva Console, navigate to the relevant **Profile**.
2. Uncheck **Backup shared data owned by other users**.
3. Click **Save**.

This prevents Druva from backing up files that are in the user's Drive but owned by someone else — reducing source data volume and avoiding duplication across multiple users' backups.

For more on Profile settings, see [Schedule Google Workspace Backups](../03-backup/GWS-03-01-schedule-backups.md).

---

## Related articles

- [Backup Policies for Google Workspace Data](../03-backup/GWS-03-04-backup-policies.md)
- [Understanding Backup Data Size Accounting](GWS-C-04-data-size-accounting.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
