# Download Google Workspace Data

**Article ID:** GWS-04-04  
**Audience:** Druva Cloud Administrators, End users  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Download backed-up Google Workspace data to your local device. Downloading differs from restoring — a restore sends data back into a Google account, while a download saves it as a file on your computer. Use downloading when you need an offline copy, want to export data for legal review, or are migrating data to another system.

Administrators can download data through the **Druva Console**. End users can download their own data through **inSync Web**.

> **📝 Note — Archive format by OS**  
> Druva automatically detects your operating system and downloads data in the appropriate archive format:
> - **macOS:** `.tar.gz` or `.tar`
> - **Windows:** `.zip`  
>  
> If a `.zip` file is too large to extract with Windows Explorer, use a third-party extraction tool such as 7-Zip.

---

## Download Gmail data (admin — Druva Console)

You can download Gmail data in **Archive**, **PST**, or **MBOX** format. PST and MBOX conversions take longer — Druva emails a download link to the administrator's registered email address when the conversion is complete.

### Download the entire mailbox

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace > Users**.
2. Click the **username** of the user whose data you want to download.
3. Click **Restore Data** and select **Gmail** as the data source.
4. Select the **snapshot** you want to download.
5. Select **all folders** and click **Download**.
6. On the **Download Data** window, select the file format:
   - **Archive** — downloads as a `.zip` (Windows) or `.tar.gz` (macOS) file.
   - **PST** — downloads as an Outlook-compatible `.pst` file.
7. Click **Download**.

> **📝 Note**  
> MBOX format is only supported for emails (Mails folder). If all folders are selected, MBOX is not available.

---

### Download emails only

1. Follow steps 1–4 above.
2. Click **Mails** and browse the mailbox, or use [Search](https://help.druva.com/en/articles/8367733-search-backed-up-data-to-download-or-restore) to find specific emails.
3. Select the emails or folders you want and click **Download**.
4. Select the file format — **Archive**, **MBOX**, or **PST** — and click **Download**.

### Download contacts only

1. Follow steps 1–4 above.
2. Click **Contacts** and select the contact group or individual contacts.
3. Click **Download**, select **Archive** or **PST**, and click **Download**.

### Download calendars only

1. Follow steps 1–4 above.
2. Click **Calendars** and select the calendar or individual events.
3. Click **Download**, select **Archive** or **PST**, and click **Download**.

> **📝 Note**  
> All Google Calendar attachments are stored in the user's Google Drive account, not within the calendar data itself.

---

## Gmail download format reference

| Data selected | Archive | MBOX | PST |
|--------------|---------|------|-----|
| Entire mailbox (Mail + Contacts + Calendar) | ✅ `.eml` | ❌ Not available | ✅ |
| Mails folder or individual emails | ✅ `.eml` | ✅ | ✅ |
| Contacts folder or individual contacts | ✅ `.vcf` | ❌ | ✅ |
| Calendars folder or individual calendar items | ✅ `.ics` | ❌ | ✅ |

---

## Download Google Drive data (admin — Druva Console)

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace > Users**.
2. Click the **username** of the user whose data you want to download.
3. Click **Restore Data** and select **Google Drive** as the data source.
4. Select the **snapshot** you want to download.
5. Browse to the files or folders you want, select them, and click **Download**.

Files download to your browser's default download location. Folders download as `.zip` files.

---

## Download Shared Drives data (admin — Druva Console)

1. Navigate to **Google Workspace > Shared Drives**.
2. Click the Shared Drive name whose data you want to download.
3. Click the **Backups** tab and select a snapshot.
4. Browse and select the files and folders, then click **Download**.

Folders download as `<folder name>.zip`.

> **📝 Note — Quarantined snapshots**  
> Snapshots marked with a 🔒 padlock icon are quarantined and cannot be downloaded. See [Ransomware Recovery for Google Workspace](https://help.druva.com/en/articles/8513175-ransomware-recovery-for-google-workspace).

---

## Download Google Workspace data (end users — inSync Web)

End users can download their own backed-up data without administrator involvement.

1. Open [inSync Web](https://help.druva.com/en/articles/8829626-access-insync-web).
2. On the menu bar, click **Data Sources**.
3. In the left pane, click **Google Workspace**.
4. In the **Documents** pane, click the row of the file or folder you want to download.
5. Click **More > Download**.

The file downloads in its original format. Folders download as `.zip` files.

> **📝 Note**  
> PST, Archive (`.eml`), and MBOX downloads are only available through the inSync Management Console, not through inSync Web.

---

## Related articles

- [Restore Gmail Data](GWS-04-01-restore-gmail.md)
- [Restore Google Drive Data](GWS-04-02-restore-drive.md)
- [Restore Shared Drives Data](GWS-04-03-restore-shared-drives.md)
- [Access Legal Hold Data via WebDAV](../07-compliance/GWS-07-02-webdav-access.md)
