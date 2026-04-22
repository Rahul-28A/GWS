# Restore Gmail Data (Mail, Contacts, Calendar)

**Article ID:** GWS-04-01  
**Audience:** Druva Cloud Administrators, End users (via inSync Web)  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Restore backed-up Gmail data — including emails, contacts, and calendar events — directly back into a user's Google account. You can restore a full mailbox, individual folders, or specific items. You can also restore data to a different user's account.

Administrators restore data using the **Druva Console**. End users can restore their own data using [inSync Web](https://help.druva.com/en/articles/8829657-restore-data-using-the-insync-web).

---

## Before you begin

- The user's Gmail is configured for backup and has at least one available snapshot.
- You have the **Druva Cloud Administrator** role (for admin-initiated restores).
- For restoring to a different user's account, that user must exist in Druva.

---

## Restore the entire mailbox

Use this option to recover all Gmail data (emails, contacts, and calendars) from a specific point in time.

1. Sign in to the **Druva Cloud Platform Console** and navigate to **Google Workspace > Users**.
2. Click the **username** of the user whose data you want to restore.
3. Click **Restore Data** and select **Gmail** as the data source.
4. Select the **snapshot** you want to restore from.
5. Select **all folders** and click **Restore**.
6. On the **Restore Data** window, select your restore options (see [Restore options reference](#restore-options-reference) below).
7. Click **Restore**.

---

## Restore emails

### Restore all emails in a folder

1. Follow steps 1–4 from the full mailbox restore above.
2. Select the **Mails** folder and click **Restore**.
3. Choose your restore options and click **Restore**.

### Restore individual emails

1. Follow steps 1–4 above.
2. Click **Mails** and browse the mailbox to find the email you want.  
   You can also use [Search](https://help.druva.com/en/articles/8367733-search-backed-up-data-to-download-or-restore) to find emails by sender, subject, or date.
3. Select the email(s) and click **Restore**.
4. Choose your restore options and click **Restore**.

During restore, Druva creates a label called `inSync-restore-<date>-<time>` in the user's mailbox and places all restored emails there.

> **📝 Note**  
> If Druva encounters a folder name longer than 255 characters, the restore may fail with `ErrorFolderSavePropertyError`. This is a Google API limitation.

---

## Restore contacts

### Restore all contacts

1. Navigate to **Google Workspace > Users**, click the username, then click **Restore Data > Gmail**.
2. Select the snapshot.
3. Select **Contacts** and click **Restore**.
4. Choose restore options and click **Restore**.

### Restore a contact group or individual contact

1. Follow the same path above, then click **Contacts** to browse.
2. Select the contact group or individual contact.
3. Click **Restore**, choose options, and click **Restore**.

For contact group restores, Druva creates a new contact group named: `<group name> (inSync Restore <date>-<time>)`.

> **📝 Note — Other Contacts restore**  
> For in-place restore of Other Contacts, data is restored to the **Others (inSync in-place Restore)** label under Contacts, rather than the actual Other Contacts section in Google, due to a Google API limitation. Only Name, Phone Number, and Email Address fields are restored.  
>  
> **Backup and restore of Other Contacts is not supported on GovCloud.**

---

## Restore calendar events

### Restore an entire calendar

1. Navigate to **Google Workspace > Users**, click the username, then click **Restore Data > Gmail**.
2. Select the snapshot.
3. Select **Calendars** and click **Restore**.
4. Choose restore options and click **Restore**.

### Restore a specific calendar or individual events

1. Follow the path above, then click **Calendars** to browse.
2. Select the calendar or individual event(s) you want to restore.
3. Click **Restore**, choose options, and click **Restore**.

Druva creates a new calendar named: `<calendar name> (inSync Restore <date>-<time>)`.

> **📝 Note — Calendar restore limitations**
> - Folder names longer than 255 characters cause an `ErrorFolderSavePropertyError` — a Google API limitation.
> - The birthday calendar is renamed **Contacts** after restore due to a Google API limitation.
> - Calendar attachments are stored in Google Drive. If an attachment was deleted from Drive, Druva cannot restore it when restoring the calendar event.
> - If you change the Gmail display language after a backup, folder names in the console will continue to display in the previous language at both the last and future restore points.
> - When a single event is deleted from a recurring series and you perform an in-place restore for the entire series, the deleted event is **not recreated**.
> - **Birthday and Task calendars are not backed up** and therefore cannot be restored.

---

## Restore options reference

When the **Restore** dialog appears, select the options that match your need:

### Restore Location

| Option | When to use |
|--------|-------------|
| **Restore to the same User Account** | You want data back in the original user's mailbox |
| **Restore to a Different User Account** | You want to send the data to another user's mailbox |

If restoring to a different account, type the user's name or email in the **Enter Name or Email** field. Druva auto-suggests matching users.

### Restore Options (same account only)

| Option | What it does |
|--------|-------------|
| **Restore as a Copy** (default) | Creates a new `inSync-Restore-<date>-<time>` folder and restores data there. Your current data is not affected. |
| **In-Place Restore** | Overwrites existing data in the user's mailbox with the selected snapshot. Use when you need to roll back to a previous state. |
| **Restore Deleted Items Only** | Available with In-Place Restore. Restores only items that were deleted, leaving current data intact. |

### Include In-Place Archive mails

Available when restoring the Mail folder only. When selected:
- **In-Place Restore** restores archived mails under the "In-Place Archive `<username>`" folder.
- **Restore as a Copy** restores data under the user's primary mailbox only.

---

## Related articles

- [Download Google Workspace Data](GWS-04-04-download-gws-data.md)
- [Restore Google Drive Data](GWS-04-02-restore-drive.md)
- [Monitor Gmail and Google Drive Backup Status](../05-monitor/GWS-05-02-monitor-gmail-drive.md)
- [Known Issues and Limitations](../08-troubleshoot/GWS-08-04-known-issues.md)
