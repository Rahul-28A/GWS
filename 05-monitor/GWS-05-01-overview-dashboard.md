# Navigate the Google Workspace Overview Dashboard

**Article ID:** GWS-05-01  
**Audience:** Druva Cloud Administrators, IT managers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

The Google Workspace Overview Dashboard gives you a real-time summary of backup health, license consumption, and workload status across Gmail, Google Drive, and Shared Drives — all in one place.

---

## Access the dashboard

1. Sign in to the **Druva Cloud Platform Console**.
2. Open the Google Workspace dashboard using either method:
   - On the homepage, click the **Google Workspace** card.
   - Click the **hamburger menu (☰)** and select **Google Workspace** under **Data Protection**.

---

## Dashboard sections

### Summary card

Displays a high-level view of backup size and app connectivity.

| Component | What it shows |
|-----------|--------------|
| **App-wise Size Distribution** | Pie chart showing the percentage of total backup data stored per workload (Gmail, Google Drive, Shared Drives). My Computer files are excluded. |
| **App Status** | Whether each workload is **Connected** (functioning) or **Not Connected** (needs reconfiguration). |
| **Last Configured** | Timestamp of the most recent successful Google Workspace configuration. |

> **📝 Note**  
> The tilde symbol (**~**) in percentage values indicates a rounded decimal. For example, `~0%` means a value less than 0.5%.

---

### Live Activity card

Shows the number of **backup** and **restore** activities currently in progress across all users and Shared Drives.

---

### License card

Displays license consumption with a **7–10 minute refresh cycle**.

| License type | What it means |
|-------------|--------------|
| **Active** | Licenses consumed by current, active users |
| **Preserved** | Licenses consumed by inactive users whose data is still retained |

**Who sees what:**

| Administrator type | What they can view |
|-------------------|--------------------|
| **Cloud Administrators** | Total allocated and consumed counts for all license types, all workloads, and all profiles |
| **Non-Cloud Admins with Manage User permission** | Consumed counts for their assigned workloads and profiles |
| **Non-Cloud Admins without Manage User permission** | Active license consumption only, for their assigned workloads and profiles |

For more on how licenses are counted, see [Understand License Consumption](GWS-05-04-license-consumption.md).

---

### Workload cards (Gmail, Google Drive, Shared Drives)

Each workload has its own card showing:

| Metric | Gmail | Google Drive | Shared Drives |
|--------|-------|-------------|--------------|
| **Total protected** | Mailboxes | Users | Shared Drives |
| **Total backup size** | ✅ | ✅ | ✅ |
| **Backup status pie chart** | Success / Failed / Backed up with Errors | Same | Same |

> **📝 Tip**  
> Click the numerical count of users or drives in any workload card to drill down into the detailed list page for that workload.

---

### Backup Data Distribution by File Type

A chart showing how backup data is distributed across different file types (PDFs, Office files, Google Docs, etc.) across all protected workloads.

---

### Backup Data Distribution by Profiles

A chart showing how backup data is distributed across the Profiles configured in your organization. Useful for identifying which Profiles consume the most storage.

---

### Daily Backup Trend

A line chart showing backup data volume over time. Hover over any point to see the storage amount backed up on that day. Useful for spotting sudden spikes or drops in backup volume.

---

### Restore Summary

Displays recent restore activity — the number of restores completed, in progress, or failed.

---

## Drill down into workload details

From the Overview Dashboard, click any workload card count to open the detailed list:

- **Gmail tab** — See [Monitor Gmail and Google Drive Backup Status](GWS-05-02-monitor-gmail-drive.md)
- **Google Drive tab** — See [Monitor Gmail and Google Drive Backup Status](GWS-05-02-monitor-gmail-drive.md)
- **Shared Drives tab** — See [Monitor Shared Drives Backup Status](GWS-05-03-monitor-shared-drives.md)

---

## Related articles

- [Monitor Gmail and Google Drive Backup Status](GWS-05-02-monitor-gmail-drive.md)
- [Monitor Shared Drives Backup Status](GWS-05-03-monitor-shared-drives.md)
- [Understand License Consumption](GWS-05-04-license-consumption.md)
- [Google Workspace Reports — Overview and Access](GWS-05-05-reports-overview.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
