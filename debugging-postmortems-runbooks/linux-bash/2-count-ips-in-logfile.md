# Scenario: "Saskatoon": counting IPs

## Description
There's a web server access log file at /home/admin/access.log. The file consists of one line per HTTP request, with the requester's IP address at the beginning of each line (first column).  
Find what's the IP address that has the most requests in this file (there's no tie; the IP is unique). Write the solution into a file /home/admin/highestip.txt.  
<b>OS</b> Debian 13

<details>
  <summary>Click here for instructions</summary>
  
## HOW-TO:
We will need to pipe multiple commands, here's the breakdown:  
1. Use awk (or cut) to extract the first IP (first field) 
```bash
# awk
awk '{ print $1 }' access.log

# cut
cat access.log | cut -d ' ' -f1
```
2. sort the IPs once to group them for counting
```bash
awk '{ print $1 }' | sort
```
This step is important, if they are not grouped, uniq won't be able to correctly count
3. Now, count with 'uniq -c'
```bash
awk '{print $1}' access.log | sort | uniq -c
```
4. Finally sort again to have them in order of number of occurences, and use head to automatically get the highest one
```bash
awk '{print $1}' access.log | sort | uniq -c | sort -nr | head -n 1
# Example Output: 482 124.147.52.111
# You can pipe a second awk to directly create the file in one command
awk '{print $1}' access.log | sort | uniq -c | sort -nr | head -n 1 | awk '{ print $2 }' > /home/admin/highestip.txt
```
- sort -nr: n will sort by numerical values and by default it will be ascending. That's why we use the reverse -r flag, so the highest count is first
</details>
