## 👨‍💻 Temporary User Creation for Developer Access (Nautilus Project)

As part of a temporary assignment to the **Nautilus Project**, a developer named `john` requires limited-time access to **App Server 2** in the **Stratos Datacenter**.

To ensure smooth access management, a temporary user account with an expiry date needs to be created.

### 📝 Task Details

- **Username:** `john`
- **Server:** `stapp02` (App Server 2)
- **Expiry Date:** `2024-02-17`
- **Naming Convention:** Use lowercase for usernames as per standard protocol.

> 📌 **Note:** Infrastructure details can be found via the **"Details of all Users and Servers"** button on the top-right section of the platform UI.

---

### 🖥️ Steps Performed

```bash
# Connect to App Server 2 via Jump Host
thor@jumphost ~$ ssh steve@stapp02.stratos.xfusioncorp.com
steve@stapp02.stratos.xfusioncorp.com's password: 
[steve@stapp02 ~]$ 

# Create the temporary user 'john' with an expiry date
[steve@stapp02 ~]$ sudo useradd -e 2024-02-17 john

# Verify user account expiry details
[steve@stapp02 ~]$ sudo chage -l john

Last password change                                    : Aug 29, 2025  
Password expires                                        : never  
Password inactive                                       : never  
Account expires                                         : Feb 17, 2024  
Minimum number of days between password change          : 0  
Maximum number of days between password change          : 99999  
Number of days of warning before password expires       : 7
