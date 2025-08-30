# Disable Direct SSH Root Login on All App Servers (Stratos Datacenter)

Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

---

```bash
thor@jumphost ~$ ssh tony@stapp01.stratos.xfusioncorp.com
tony@stapp01.stratos.xfusioncorp.com's password: 

[tony@stapp01 ~]$ sudo vi /etc/ssh/sshd_config
[sudo] password for tony: 

Locate the line:
#PermitRootLogin yes

Modify it to:
PermitRootLogin no

[tony@stapp01 ~]$ sudo systemctl restart sshd

Verify the change:
[tony@stapp01 ~]$ sudo grep PermitRootLogin /etc/ssh/sshd_config

#It should show result something like this - 
PermitRootLogin no
# the setting of "PermitRootLogin without-password".
[tony@stapp01 ~]$ 

#Repeat on All App Servers
#Perform all of the above steps on each app server within the Stratos Datacenter