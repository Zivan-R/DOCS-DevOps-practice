# Scenario: "Saint John": what is writing to this log file?

## Description:  
A developer created a testing program that is continuously writing to a log file /var/log/bad.log and filling up disk. You can check for example with tail -f /var/log/bad.log.
This program is no longer needed. Find it and terminate it. Do not delete the log file.
  
<b>OS</b>: Debian 11
  
<details>
  <summary>Click here for solution</summary>
  
## Solution:

1. List all processes to see if you can find something related  
```bash
ps auxf
```
- a: shows processes from all users that are attached to a terminal
- u: user-oriented format. Shows detailed columns (USER, %CPU, %MEM, VSZ, RSS, START, COMMAND
- x: include no-terminal processes (daemons/bg processes not attached to a TTY)
- f: Forest/tree view. Displays parent-child process relationships
2. Use fuser (or lsof) to quickly find the process and note its PID
```bash
fuser /var/log/bad.log
```
3. Using the PID found, terminate (kill) the process
```bash
# Example
kill -9 587
```
</details>
