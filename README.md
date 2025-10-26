# Task 4: Firewall Configuration and Testing (Linux - UFW)

## Objective
The objective of this task is to configure and test basic firewall rules on Linux using **UFW (Uncomplicated Firewall)** to understand network traffic filtering and improve system security.

## Overview
A firewall monitors and controls network traffic based on predefined security rules. This task demonstrates:
- Blocking insecure services such as Telnet (port 23)
- Allowing secure access through SSH (port 22)
- Listing and managing active firewall rules

---

## Tools Used
- **Operating System:** Kali Linux 
- **Firewall Utility:** UFW (Uncomplicated Firewall)
- **Testing Tool:** Telnet

---

## Steps Performed

### 1. Install and Enable UFW
```
sudo apt update && sudo apt install ufw -y
sudo ufw enable
```

### 2. Set Default Policies
```
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

### 3. Verify Firewall Status
```
sudo ufw status verbose
```

### 4. Block Telnet (Port 23)
```
sudo ufw deny 23
```

### 5. Allow SSH (Port 22)
```
sudo ufw allow 22/tcp
```

### 6. Test Block Rule
```
telnet localhost 23
```
Expected result: *Connection refused* — confirms port 23 is blocked.

### 7. Remove Test Rule
```
sudo ufw delete deny 23
```

---

## Deliverables
| File | Description |
|------|--------------|
| `firewall_rules_backup.txt` | Contains example of active UFW rules configuration |
| `firewall_commands.txt` | Contains all terminal commands used during configuration |
| `screenshots/` | Screenshots of terminal outputs |

Example rule output for submission:
```
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 23                         DENY IN     Anywhere                  
[ 2] 22/tcp                     ALLOW IN    Anywhere                  
[ 3] 23 (v6)                    DENY IN     Anywhere (v6)             
[ 4] 22/tcp (v6)                ALLOW IN    Anywhere (v6)      
```

---

## Outcome
Successfully demonstrated basic firewall management:
- Configured traffic filtering using UFW
- Blocked insecure connections (Telnet)
- Allowed secure connections (SSH)
- Verified and documented network security rules

---

## Author
**Name:** Medikonda Pradeep        
**Internship Program:** Cyber Security Internship  
**Date:** 26 October 2025  
**Platform:** GitHub  
