# User Mapping Logic (Email ID vs. AD Attribute vs. UPN)

**Article ID:** GWS-C-05  
**Audience:** Administrators, IT architects  
**License:** For license details, see [Plans & Pricing](https://www.druva.com/products/pricing-plans/).

---

Before Druva can back up a user's Google Workspace data, it needs to match the user's inSync account to their Google Workspace account. This matching process is called **user mapping**. If mapping is incorrect or misconfigured, backups fail with a `USER NOT FOUND` error.

This article explains how each mapping method works, when to use it, and how to troubleshoot mismatches.

---

## How user mapping works

Every inSync user has an identity — typically an email address. Every Google Workspace account also has an identity — a Google email address or, in AD-integrated environments, a User Principal Name (UPN). Druva uses one of two methods to match these two identities.

```
inSync User ──────────────────────────► Google Workspace Account
   (email or UPN)          [mapping method]       (Gmail account)
```

If the mapping finds a match, Druva accesses that user's Google data for backup. If no match is found, the backup fails.

---

## Method 1 — Email address (default)

**How it works:** Druva compares the inSync user's **email address** directly against Google Workspace account email addresses. An exact match is required.

**Example:**

| inSync user email | Google account email | Result |
|------------------|---------------------|--------|
| `alice@company.com` | `alice@company.com` | ✅ Match — backup succeeds |
| `alice@company.com` | `alice@workspace.com` | ❌ No match — `USER NOT FOUND` |

**When to use:** Your inSync users and your Google Workspace accounts share the same email domain. This covers the majority of organizations.

**When it fails:** Your organization uses a custom domain in Google Workspace that is different from the domain used in inSync. In this case, configure a **custom domain** to tell Druva which Google domain to use. See [Configure User Mapping and Custom Domains](../02-setup/GWS-02-02-user-mapping-custom-domains.md).

---

## Method 2 — AD Attribute (User Principal Name / UPN)

**How it works:** Druva reads the **User Principal Name (UPN)** from your Active Directory (AD) or LDAP integration and uses it to look up the corresponding Google Workspace account.

**Example:**

| inSync user (from AD) | UPN in AD | Google account looked up | Result |
|----------------------|-----------|-------------------------|--------|
| Alice Smith | `alice@company.com` | `alice@company.com` in Google Workspace | ✅ Match |

**When to use:**
- Your organization manages users through Active Directory or LDAP.
- User identity in AD (UPN) maps naturally to Google Workspace account emails.
- You want Druva to automatically pick up user identity changes from AD without manual updates.

**Prerequisite:** Active Directory or LDAP must be integrated with inSync, and an AD Mapping must be configured to fetch user accounts. See [Create an AD/LDAP Mapping](https://help.druva.com/en/articles/8702705-create-an-ad-ldap-mapping).

---

## Custom domain — solving domain mismatch

If inSync user emails and Google Workspace account emails use **different domains**, Druva cannot match them by default. The custom domain setting tells Druva to substitute the Google Workspace domain when looking up users.

**Example scenario:**

- inSync users have `@company.com` email addresses.
- Google Workspace accounts use `@company.workspace.com`.
- Without custom domain: `alice@company.com` does not match `alice@company.workspace.com` → backup fails.
- With custom domain set to `company.workspace.com`: Druva looks up `alice@company.workspace.com` → backup succeeds.

To configure: see [Configure User Mapping and Custom Domains](../02-setup/GWS-02-02-user-mapping-custom-domains.md).

---

## Storage note

Google Workspace backup data is charged against the **Organization Quota** in Druva, not individual user backup quotas. This is true regardless of which mapping method is used.

---

## Troubleshooting mapping failures

| Symptom | Likely cause | Fix |
|---------|-------------|-----|
| `USER NOT FOUND` for all users | Domain mismatch — inSync and Google Workspace use different email domains | Configure a custom domain in Cloud App Settings |
| `USER NOT FOUND` for specific users | Those users have different email addresses in inSync vs. Google Workspace | Update the user's email in inSync to match their Google account, or adjust the AD mapping |
| Backup works for some users, not others | Partial domain mismatch, or some users imported with wrong email | Review each failing user's inSync email against their Google account |
| UPN-mapped users not being picked up | AD mapping not configured, or AD sync has not run | Verify the AD/LDAP mapping is active and trigger a sync |

---

## Decision guide — which method to choose

```
Does your organization use Active Directory or LDAP for identity management?
│
├── YES → Use AD Attribute (UPN) method
│          Prerequisite: Configure AD/LDAP integration and AD mapping in inSync
│
└── NO  → Use Email Address method (default)
           │
           ├── Same domain in inSync and Google Workspace?
           │    └── YES → No additional config needed
           │
           └── Different domains?
                └── YES → Configure a custom domain in Cloud App Settings
```

---

## Related articles

- [Configure User Mapping and Custom Domains](../02-setup/GWS-02-02-user-mapping-custom-domains.md)
- [Set Up Google Directory User Provisioning](../02-setup/GWS-02-05-google-directory-provisioning.md)
- [Troubleshoot Google Workspace Backup Errors](../08-troubleshoot/GWS-08-01-troubleshoot-backup-errors.md)
- [Google Workspace Backup with Druva — Overview](../01-getting-started/GWS-01-01-overview.md)
