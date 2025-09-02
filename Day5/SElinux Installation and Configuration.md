# Disable SELinux on App Server 2 (Stratos Datacenter)

## Objective

Following a security audit, the xFusionCorp Industries security team has decided to temporarily disable SELinux on App Server 2 (`stapp02`) to prepare for future configuration changes.

This document outlines the steps taken to:

- Install necessary SELinux packages
- Permanently disable SELinux (without requiring immediate reboot)

---

## Server Details

- **Server Name:** App Server 2  
- **Hostname:** `stapp02.stratos.xfusioncorp.com`  
- **User:** `banner`  
- **Task Date:** September 1, 2025

---

## Steps Performed

### 1. SSH into App Server 2

```bash
ssh banner@stapp02.stratos.xfusioncorp.com
```

### 2. Install SELinux Packages

```bash
sudo yum install -y selinux-policy selinux-policy-targeted
```

### 3. Disable SELinux Permanently

Edit the SELinux configuration file:

```bash
sudo vi /etc/selinux/config
```

Change the following line:

```
SELINUX=enforcing
```

To:

```
SELINUX=disabled
```

### 4. Confirm Configuration Change

```bash
grep SELINUX= /etc/selinux/config
```

**Expected Output:**

```
SELINUX=disabled