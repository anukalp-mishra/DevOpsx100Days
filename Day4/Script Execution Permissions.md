# Grant Executable Permissions to `xfusioncorp.sh` on App Server 3

## Task Summary

In order to automate backup processes, the xFusionCorp Industries sysadmin team created a script named `xfusioncorp.sh`. This script has been distributed across all necessary servers, but was missing executable permissions on **App Server 3** (`stapp03`) in the **Stratos Datacenter**.

This document outlines the steps taken to grant executable permissions to the script, ensuring that **all users** are able to execute it.

---

## Server Details

- **Server Name:** App Server 3  
- **Hostname:** `stapp03.stratos.xfusioncorp.com`  
- **User:** `banner`  
- **Script Location:** `/tmp/xfusioncorp.sh`

---

## Objective

Ensure the script `/tmp/xfusioncorp.sh` is executable by **all users**.

---

## Steps Performed

1. **SSH into App Server 3:**

    ```bash
    thor@jumphost ~$ ssh banner@stapp03.stratos.xfusioncorp.com
    ```

2. **Switch to the `/tmp` directory (optional):**

    ```bash
    cd /tmp
    ```

3. **Grant read and execute permissions to all users:**

    ```bash
    sudo chmod a+rx /tmp/xfusioncorp.sh
    ```

4. **Verify permissions:**

    ```bash
    ls -l /tmp/xfusioncorp.sh
    ```

    **Expected output:**

    ```bash
    -r-xr-xr-x 1 root root 40 Sep  1 18:41 /tmp/xfusioncorp.sh
    ```

---

## Result

The `xfusioncorp.sh` script now has executable permissions for **owner**, **group**, and **others**, fulfilling the task requirements.

---

## Notes

- The `a+rx` flag ensures that **all users** (`a`) have **read** (`r`) and **execute** (`x`) permissions.
- This approach is useful in shared environments where scripts need to be accessible system-wide.

---

## Author

*Task performed by:* `Anukalp`  
*Date:* `September 1, 2025`