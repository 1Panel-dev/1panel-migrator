## 🚀 Upgrade Guide

The upgrade process has two steps: **upgrade services** and **upgrade websites**.

> Complete the service upgrade before upgrading websites.

Service upgrade includes two roles:

- **Primary node**: includes both `1panel-core` and `1panel-agent`, exposes external ports, and supports browser access.
- **Secondary node**: includes only `1panel-agent`, does not expose external ports, and must be added and managed from the primary node's `Node Management` page.

---

### Upgrade as Primary Node

#### Step 1: Upgrade Services

```bash
1panel-migrator upgrade core
```

#### Step 2: Upgrade Websites

> Note: Make sure V2 services have started successfully before running this command.

```bash
1panel-migrator upgrade website
```

### Upgrade as Secondary Node

#### Step 1: Upgrade Services

```bash
1panel-migrator upgrade agent
```

#### Step 2: Add the Secondary Node on the Primary Node

Go to the primary node's **Node Management** page and add this secondary node. The system will automatically identify and process V1 historical data.

#### Step 3: Upgrade Websites

> Note: After the secondary node is added, run the website upgrade command on the secondary node server.

```bash
1panel-migrator upgrade website
```
