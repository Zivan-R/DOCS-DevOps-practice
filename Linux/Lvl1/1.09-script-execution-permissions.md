# 1.9 Script Execution Permissions
---
## Task
In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 3 within the Stratos Datacenter.
  
Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 3. Additionally, ensure that all users have the capability to execute it.
## Solution
1. SSH into server
2. Grant permissions to the script
```bash
sudo chmod +rx /tmp/xfusioncorp.sh
# Note that reading permission is required to execute the file
```
3. Check
```bash
ls -l /tmp/xfusioncorp.sh

# You can also try to run the script
sh /tmp/xfusioncorp.sh
```
