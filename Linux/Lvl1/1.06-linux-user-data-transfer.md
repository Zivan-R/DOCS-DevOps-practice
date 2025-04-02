# 1.6 Linux User Data Transfer
---
## Task
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus App Server 2 at the /home/usersdata location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:  
  
Locate all files (excluding directories) owned by user ravi within the /home/usersdata directory on App Server 2. Copy these files while preserving the directory structure to the /beta directory.
## Solution
1. SSH into server 2
2. Use find command to filter the files and -exec cp to copy
```bash
sudo find /home/usersdata -type f -user ravi -exec cp --parents {} /beta/ \;
```
3. Explanations of the command for future reference
```bash
sudo find /home/usersdata -type f -user ravi
```  
Will look in /home/usersdata only for files owned by ravi  
```bash
-exec cp --parents {} /beta/ \;
```
For each file found (placeholder is {}), execute cp (copy) while preserving directory structure (--parents) to the target directory (/beta/)  
### NOTE
This will copy directory structure from /home, meaning the target dir will be /beta/home/usersdata/files.  
For reference, to avoid this behavior and only copy the contents of /home/usersdata with find:  
```bash
# First cd into the directory
cd /home/usersdata
# And then copy the data with find
sudo find . -type f -user ravi -exec cp --parents {} /news/ \;
```
