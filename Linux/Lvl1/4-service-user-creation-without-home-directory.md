# 1.4 Service User Creation without Home Directory
---
## Task
In response to the latest tool implementation at xFusionCorp Industries, the system admins require the creation of a service user account. Here are the specifics:  
  
Create a user named kareem in App Server 2 without a home directory.  
## Solution
1. SSH into the remote server
2. Create the service user account without a home directory
```bash
sudo useradd -r -M kareem
```
3. Verify user's home directory doesn't exist
```bash
ls -ld /home/kareem
# Expected output:
# ls: cannot access '/home/kareem': No such file or directory
```
