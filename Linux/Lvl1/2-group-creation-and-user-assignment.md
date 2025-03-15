# 1.2 Group Creation and User Assignment
---
## Task
The system admin team at xFusionCorp Industries has streamlined access management by implementing group-based access control. Here's what you need to do:  
  
a. Create a group named nautilus_noc across all App servers within the Stratos Datacenter.  
b. Add the user mohammed into the nautilus_noc group on all App servers. If the user doesn't exist, create it as well.  

## Solution
**After checking /etc/os-release, the distribution is confirmed to be Centos**  
  
1. SSH into the server
2. Check if the nautilus_noc group already exists
```bash
getent group nautilus_noc
```
3. If it doesn't exist, create it
```bash
sudo groupadd nautilus_noc
```
4. Check if user mohammed exists
```bash
id mohammed
```
5. If not, create it and assign the nautilus_noc group
```bash
sudo useradd -m -G nautilus_noc mohammed
```
6. Check if user was created successfuly and added to the correct group
```bash
id mohammed
```
7. If needed, ensure mohammed is part of nautilus_noc group
```bash
sudo usermod -aG nautilus_noc mohammed
```
8. Repeat for each app server
