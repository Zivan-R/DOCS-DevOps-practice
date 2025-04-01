# 1.1 Custom Apache user setup
---
## Task:
In response to heightened security concerns, the xFusionCorp Industries security team has opted for custom Apache users for their web applications.  
Each user is tailored specifically for an application, enhancing security measures.  
Your task is to create a custom Apache user according to the outlined specifications:   
- a. Create a user named rose on App server 2 within the Stratos Datacenter.
- b. Assign a unique UID 1925 and designate the home directory as /var/www/rose.

## Solution:

1. SSH into the server using the logs provided in the documentation  
2. Check the Linux distribution  
```bash
cat /etc/os-release
```
3. Create custom user  
```bash
sudo useradd -u 1124 -m -d /var/www/yousuf yousuf
```
4. Set password for new user
```bash
sudo passwd yousuf
```
