## 🔒 Create Non-Interactive User for Backup Agent (Nautilus Project)

To meet the specifications of the **backup agent tool**, the system administration team at **xFusionCorp Industries** requested the creation of a user with a **non-interactive shell**.

This ensures the user can exist for background operations without being able to log in interactively.

### 📝 Task Details

- **Username:** `mariyam`
- **Server:** `stapp03` (App Server 3)
- **Shell Type:** `/sbin/nologin` (non-interactive)
- **Purpose:** Background process access (e.g., backup agent)

> 📌 **Note:** You can find infrastructure details by clicking the **"Details of all Users and Servers"** button on the top-right section of the page.

---

### 🖥️ Steps Performed

```bash
# Connect to App Server 3 from Jump Host
thor@jumphost ~$ ssh banner@172.16.238.12
banner@172.16.238.12's password: 

# Create user 'mariyam' with a non-interactive shell
[banner@stapp03 ~]$ sudo adduser -s /sbin/nologin mariyam
[sudo] password for banner: 