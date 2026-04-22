# Google Workspace Reports — Overview and Access

**Article ID:** GWS-05-05  
**Audience:** Druva Cloud Administrators, IT managers  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Druva provides a centralized reporting suite for Google Workspace on the **Druva Cloud Platform (DCP) Console**. These reports give visibility into backup health, license usage, restore activity, user provisioning, and storage trends — with advanced filtering, sorting, and scheduled email delivery.

> **📝 Note — Legacy reports deprecated**  
> All legacy reports within the Google Workspace Console were deprecated in March 2026. Use the centralized reports at the DCP level instead. To access them, go to **Left navigation menu > Reports** in the Druva Cloud Platform Console.

---

## Available Google Workspace reports

| Report name | What it shows |
|-------------|--------------|
| **User Workload Report** | Backup status and data size per user, per workload |
| **User Last Backup Status Report** | Most recent backup outcome for each user |
| **User Restore Activity Report** | All restore operations — who restored what, when, and to where |
| **Users Count & Status Report** | Total user counts broken down by Active, Preserved, and Disabled status |
| **License Usage Report** | Active and Preserved license consumption over time |
| **Alert History Report** | Log of all alerts triggered, with severity and resolution status |
| **Storage Consumption Report** | Storage used per profile, per workload, and over time |
| **User Provisioning Report** | Users imported via each provisioning method, including the mapping used |
| **Preserved Users Datasources Report** | Data sources belonging to preserved users |
| **Google Shared Drive Backup Activity Report** | Per-drive backup activity log |
| **Google Shared Drive Restore Activity Report** | Per-drive restore activity log |

---

## Access the reports

1. Sign in to the **Druva Cloud Platform Console**.
2. In the left navigation menu, click **Reports**.
3. Select the report you want to view.

---

## Subscribe to a report

You can subscribe to any report to receive it by email on a schedule.

1. Navigate to **Reports** in the DCP Console.
2. Open the report you want to subscribe to.
3. Click **Subscribe** (or **Manage Subscriptions**).
4. Set the frequency and recipient email addresses.
5. Click **Save**.

For detailed subscription steps, see [Manage Reports](https://help.druva.com/en/articles/12107637-manage-reports).

---

## API access for reports

All Google Workspace reports support API access for integration with external dashboards or SIEM tools.

| Report | API name |
|--------|---------|
| Alert History Report | `googleAlerts` |
| License Usage Report | `googleLicenseUsage` |
| Preserved Users Datasources Report | `googlePreservedUsersDatasources` |
| Google Shared Drive Backup Activity Report | `googleSharedDriveBackupActivity` |
| Google Shared Drive Restore Activity Report | `googleSharedDriveRestoreActivity` |
| Storage Consumption Report | `googleStorageConsumption` |
| Users Count & Status Report | `googleUserCountAndStatus` |
| User Last Backup Status Report | `googleUserLastBackupStatus` |
| User Provisioning Report | `googleUserProvisioning` |
| User Restore Activity Report | `googleUserRestoreActivity` |
| User Workload Report | `googleUserWorkload` |

For API documentation, see the [Druva Developer Portal](https://developer.druva.com/reference/choose-your-druva-product).

---

## Related articles

- [Navigate the Google Workspace Overview Dashboard](GWS-05-01-overview-dashboard.md)
- [Understand License Consumption](GWS-05-04-license-consumption.md)
- [Manage Reports](https://help.druva.com/en/articles/12107637-manage-reports)
