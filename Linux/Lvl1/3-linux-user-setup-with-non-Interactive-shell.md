# 1.3 Linux User Setup with Non-Interactive Shell
---
## Task
To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:  
  
Create a user named james with a non-interactive shell on App Server 1.  
  
## Solution

1. SSH into the App Server 1
2. Verify if user james already exists
```bash
getent passwd james
```
3. If user exists, modify it
```bash
sudo usermod -s /sbin/nologin james
```
4. Else, create user james with a Non-Interactive default shell
```bash
sudo useradd -s /sbin/nologin james
```
5. Check if james has the correct configuration
```bash
getent passwd james
# OR
cat /etc/passwd | grep james
```
6. Try switching to the user james (The access should be denied)
```bash
sudo su - james
# Expected output: "This account is currently not available."
```
