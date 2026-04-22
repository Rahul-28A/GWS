# Backup Policies for Google Workspace Data

**Article ID:** GWS-03-04  
**Audience:** Druva Cloud Administrators  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Backup policies are defined in a **Profile** and control how Druva backs up, retains, and restricts access to Google Workspace data. Every user assigned to a Profile is governed by that Profile's policies.

This article explains each policy type, what it controls, and where to configure it.

---

## Backup frequency policy

**What it controls:** How often Druva backs up Gmail and Google Drive data for users in this Profile.

**How it works:** You set a backup interval (for example, every 12 hours or once daily). Druva runs the backup on schedule as long as at least one Google Workspace device is online.

**Where to configure:** In the Profile under **SaaS Apps > Backup Interval**.  
See [Define the backup interval for SaaS Apps](https://help.druva.com/en/articles/8702806-define-the-backup-interval-and-the-schedule-user-devices-and-saas-apps).

---

## Retention policy

**What it controls:** How long Druva keeps backup snapshots in storage before automatically deleting them.

**How it works:** You can set retention periods for daily, weekly, and monthly snapshots independently. Once a snapshot exceeds its retention period, Druva deletes it from storage. Setting the value to `0` retains backups indefinitely.

> **⚠️ Important**  
> Druva uses an **incremental forever** backup model. After the first full backup, only changed data is backed up. Snapshots accumulate over the retention period. Files deleted by the user are still retained in Druva until the snapshot they were in expires.

**Where to configure:** In the Profile under **Retention Settings**.  
See [Configure the backup retention policy](https://help.druva.com/en/articles/8367724-configure-the-backup-retention-policy).

---

## Data privacy policy

**What it controls:** Who in your organization can view backed-up user data in the Druva Console.

**How it works:** For a Profile, SaaS Apps and endpoint devices share the same privacy policy. Depending on the policy, administrators may or may not be able to browse individual users' backed-up content.

**Where to configure:** In the Profile under **Data Privacy**.  
See [Configure the user data privacy policy](https://help.druva.com/en/articles/8702770-configure-the-user-data-privacy-policy).

---

## Global exclusion policy

**What it controls:** File types and folder paths that Druva skips during all backups for users in this Profile.

**How it works:** You specify file extensions (for example, `.mp4`, `.iso`) or absolute folder paths (for example, `My Drive/Videos`) that Druva should exclude. Exclusions apply to both Gmail and Google Drive backups.

**Where to configure:** In the Profile under **Global Exclusions**.  
See [Configure the global exclude list](https://help.druva.com/en/articles/8702773-configure-the-global-exclude-list).

---

## Shared Drives — separate policy configuration

Shared Drives do not use Profile-level backup policies. Instead, each Shared Drive has its own backup and retention settings configured directly in the Shared Drives section. You can use the **Auto Configuration** defaults or set **Custom** settings per drive.

See [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md).

---

## Policy precedence

When both a Profile-level global exclusion and a Shared Drive exclusion are configured, each applies independently to its respective workload:

- **Profile exclusions** → apply to Gmail and Google Drive.
- **Shared Drive exclusions** → apply to that specific Shared Drive only.

---

## Related articles

- [Schedule Google Workspace Backups](GWS-03-01-schedule-backups.md)
- [Set Up and Configure Shared Drives Backup](../02-setup/GWS-02-04-shared-drives-setup.md)
- [Why Does Druva Show More Data Than Google Storage?](../09-concepts/GWS-C-04-data-size-accounting.md)
