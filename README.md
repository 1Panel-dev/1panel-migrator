## ⚠️ Before You Start

**1panel-migrator** is the official migration tool for smoothly upgrading from **1Panel V1** to **1Panel V2**.

To ensure a safe and successful migration, please read the following notes carefully before you begin.

---

### Create a Snapshot in Advance

To reduce risks from unexpected issues, it is strongly recommended to:

- Sign in to **1Panel Console -> Panel Settings** and create a system snapshot manually.
- Or create a cloud server snapshot through your cloud provider.

### Required V1 Version

Migration is supported only for **1Panel `v1.10.29-lts` and later**.

### Target V2 Version After Migration

After migration, the system will be upgraded to **1Panel v2.1.2**.

### Pro Edition and Licenses

- Existing licenses will be cleared, and the system will be migrated to the **Community Edition**.
- One-time purchase licenses from V1 cannot be used in V2.
- Lifetime licenses have no version restriction and do not require an upgrade.

### Websites

#### Website Root Directory Migration

After migration, **all website data will be stored in `{1Panel installation directory}/www`**.

> Example: `/opt/1panel/www`

#### OpenResty Version

The system will be automatically upgraded to **OpenResty `1.27.1.2-0-1-focal`**.

#### OpenResty Main Configuration

- `1panel-migrator upgrade website` resets the OpenResty main configuration file. If you have custom changes, back it up in advance.
- If you need HTTP/3 after the upgrade, it is recommended to uninstall and reinstall OpenResty (existing websites will not be deleted).

#### Websites Using PHP Runtime

- The built-in PHP runtime in the panel will be removed.
- **PHP containers of existing websites will not be deleted** and will be migrated as static websites.
- You can create a V2 PHP runtime later, then switch migrated static websites back to PHP websites in the original site settings.

#### Reverse Proxy Websites

V2 refactors the reverse-proxy cache mechanism so each website uses an independent directory. Before running `1panel-migrator upgrade website`, make sure reverse-proxy caching is disabled for all websites.

### Backup Records

For compatibility reasons:

- All **V1 backup records for websites, applications, and databases will be cleared**.
- Reconfigure backup strategies after migration.

### Host Terminal

Host lists, groups, and quick commands are migrated only when upgrading as a primary node. If upgrading as a secondary node, this data is not migrated.

### Scheduled Tasks

- **Scheduled tasks themselves are migrated**.
- **Task execution history is not retained**.

### Snapshots

Due to version mechanism differences, **V1 snapshot records cannot be migrated to V2**.

### Panel Settings

After the upgrade, panel settings for all nodes will follow the current V2 primary node configuration.

### WAF and Website Monitoring

Due to architecture changes:

- **Most V1 WAF configurations and website monitoring records are incompatible** and will not be migrated.
- WAF preserves only: allow/block lists, IP groups, and custom rules.
- Reconfigure related features after migration.

### Feedback

If you encounter issues or have feedback, please submit an issue in the [1Panel main repository](https://github.com/1Panel-dev/1Panel/issues).

## 📚 Documentation

### Installation Guide

- [Installation Guide](install.md)

Learn how to download and install the `1panel-migrator` tool.

### Upgrade Guide

- [Upgrade Guide](upgrade.md)

Detailed steps for upgrading 1Panel from V1 to V2, including both primary and secondary nodes.

### Rollback Guide

- [Rollback Guide](rollback.md)

How to roll back services and websites if the upgrade fails or recovery is required.
