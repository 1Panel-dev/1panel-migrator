# ℹ️ Rollback Guide

The rollback process also has two steps: **roll back 1Panel services** and **roll back websites**.

> Complete the service rollback before rolling back websites.

---

### Service Rollback

No distinction is made between primary and secondary nodes. Run the following command directly on the target server:

```bash
1panel-migrator rollback service
```

### Website Rollback

Run the following command on the target server:

> Note: Make sure V1 services have started successfully before running this command.

```bash
1panel-migrator rollback website
```
