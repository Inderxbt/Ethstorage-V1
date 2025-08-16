# EthStorage V1 Trusted Setup Ceremony — Participant Guide

This document provides a step-by-step guide to help you securely participate in the **EthStorage V1 Trusted Setup Ceremony**.

---

## 📌 System Requirements

* **Operating System**: Ubuntu 22.04 (VPS recommended)
* **Hardware**: 2 vCPU, 4 GB RAM, 30 GB+ SSD
* **Access**: Basic SSH access
* **GitHub Account** (required for authentication)

  * Minimum account age: **1 month**
  * At least **1 public repository**
  * Must **follow ≥ 5 accounts** and have **≥ 1 follower**
  * Gist read/write permission enabled for the tool

---

## 🛠 Installation & Setup

### 1️⃣ Update System and Install Dependencies

```bash
sudo apt update && apt upgrade -y
sudo apt install -y curl git build-essential
```

### 2️⃣ Install Node.js v18 and npm v9.2

```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install -y nodejs
npm install -g npm@9.2
```

### 3️⃣ Verify Installed Versions

```bash
node -v
npm -v
```

### 4️⃣ Create a Temporary Working Directory

```bash
mkdir ~/trusted-setup-tmp && cd ~/trusted-setup-tmp
```

### 5️⃣ Install Phase2 CLI

```bash
npm install -g @p0tion/phase2cli
```

### 6️⃣ Confirm CLI Installation

```bash
phase2cli --version
```

### 7️⃣ Authenticate via GitHub

```bash
phase2cli auth
```

* Open the browser link displayed in the terminal
* Log in to GitHub and authorize **p0tion** to access Gists
* Return to the terminal once authorization is complete

### 8️⃣ Contribute to the Ceremony

Start a screen session to ensure continuity:

```bash
screen -S ceremony
```

Run the contribution command:

```bash
phase2cli contribute -c ethstorage-v1-trusted-setup-ceremony
```

---

##  Remove The Login Permissions After Contribution From vps

After completing your contribution, run:

```bash
phase2cli clean
phase2cli logout
cd ~ && rm -rf ~/trusted-setup-tmp
```

---

## 🖥 Screen Session Management

* **Detach**: `CTRL + A`, then `D`
* **Reattach**:

```bash
screen -r ceremony
```

---

## ✅ Completion

* After executing the above steps, you will be placed in the contribution queue.
* Once your turn arrives, the tool will automatically process your contribution.
* 🎉 Congratulations! You have successfully contributed to the **EthStorage V1 Trusted Setup Ceremony**.

