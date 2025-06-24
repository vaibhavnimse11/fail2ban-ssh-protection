# fail2ban-ssh-protection
A Debian-based practical setup using Fail2Ban to automatically block IP addresses after multiple failed SSH login attempts, enhancing server security against brute-force attacks.
# Fail2Ban SSH Protection on Debian

This project demonstrates how to secure a Debian-based Linux system using **Fail2Ban** by automatically blocking IP addresses that attempt multiple failed SSH login attempts.

---

##  Objective

To **detect and block brute-force attacks** on SSH by banning any IP address that tries to access the system with invalid credentials more than 3 times within a specified time.

---

##  Tools Used

- **OS:** Debian Linux
- **Security Tool:** Fail2Ban

---

## ⚙️ Configuration Details

Fail2Ban was configured with the following settings in `/etc/fail2ban/jail.local`:

```ini
[sshd]
enabled = true
port = 22
filter = sshd
backend = systemd
maxretry = 3
bantime = 3600
findtime = 600
