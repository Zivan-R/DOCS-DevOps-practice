# Day 1: Linux User Setup with Non-Interactive Shell
---
## Task
To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:

Create a user named mariyam with a non-interactive shell on App Server 3.

<details>
  <summary>Click here for solution</summary>
  
## Solution
1. SSH into App Server 3
2. Create user with non interactive default shell
```bash
sudo useradd -s /sbin/nologin mariyam
```
3. Check
```bash
getent passwd mariyam
```
</details>
