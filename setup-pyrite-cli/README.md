# 🚀 Setup Pyrite CLI

Install the **Pyrite Cloud CLI** in your GitHub Actions workflow using the official installer.

This action provides a fast, reliable, and CI-friendly way to set up the Pyrite CLI with zero external dependencies.

---

## ✨ Features

- ⚡ Uses the official installer from Pyrite releases
- 📦 Supports installing a specific version or `latest`
- 🧩 No Node.js or Homebrew required
- 🔁 Works across GitHub-hosted and self-hosted runners
- 🛠 Compatible with minimal environments (including `act`)

---

## 📦 Usage

### Basic

```yaml
steps:
  - uses: actions/checkout@v4

  - name: Setup Pyrite CLI
    uses: pyritecloud/actions/setup-pyrite-cli@main

  - name: Check version
    run: pyrite --version
```

---

### Install Latest Version

```yaml
- name: Setup Pyrite CLI
  uses: pyritecloud/actions/setup-pyrite-cli@main
  with:
    version: latest
```

---

### Install Specific Version

```yaml
- name: Setup Pyrite CLI
  uses: pyritecloud/actions/setup-pyrite-cli@main
  with:
    version: v0.1.3
```

---

## ⚙️ Inputs

| Name    | Description                               | Required | Default  |
| ------- | ----------------------------------------- | -------- | -------- |
| version | Version to install (`vX.Y.Z` or `latest`) | ❌       | `latest` |

---

## 🔐 CI Behavior

This action runs the installer in **CI-safe mode**, meaning:

- ❌ It does **not modify shell configuration files** (`.bashrc`, `.zshrc`, etc.)
- ✅ It is safe to run in CI/CD environments without side effects

---

## 🧪 Local Testing with act

If you are using `act`, use a full-featured runner image:

```bash
act -P ubuntu-latest=ghcr.io/catthehacker/ubuntu:act-latest
```

---

## 📄 License

MIT License © Pyrite Cloud
