## 🛠️ Installation Guide

### Download the Package

Visit the Gitee release page, manually download the package for your server architecture, and place it in `/tmp`:

> 🔗 https://gitee.com/fit2cloud-feizhiyun/1panel-migrator/releases/

Each release provides packages for the following architectures (example file names):

- `1panel-migrator-linux-amd64`
- `1panel-migrator-linux-arm64`
- `1panel-migrator-linux-arm`
- `1panel-migrator-linux-ppc64le`
- `1panel-migrator-linux-s390x`

---

### Installation Steps (amd64 Example)

```bash
# 1. Enter the temporary directory
cd /tmp

# 2. Add execute permission
chmod +x 1panel-migrator-linux-amd64

# 3. Move to system PATH and rename
mv 1panel-migrator-linux-amd64 /usr/local/bin/1panel-migrator
```
