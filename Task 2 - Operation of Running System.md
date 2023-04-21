### Operation of Running System.

A. Create a bash shell script named certscript.sh under /home/student/apps/.

1. Make sure the script can be invoked as ./certscript.sh.
2. The first line of output from the script should consist of the name of the user who invoked it.
3. The second line of output should contain the IP address of the default gateway.
---
### Solution

- ```touch /home/student/apps/certscript.sh```
- ```chmod +x /home/student/apps/certscript.sh```
- Enter the file: ```bash nano /home/student/apps/certscript.sh ```
- Type the following into the file
```Shell
#!/bin/bash
echo $USER
echo $(ip route show default| awk'{print $3; exit}')
```
---
### Operation of Running System 2.

1. Install the tmux package on your system.
2. Create a cron job that kills all processes named scan_filesystem which is owned by root, every minute.

### Solution

```Shell
#!/bin/bash
touch install.sh && chmod +x installl.sh
sudo apt-get install -qq && sudo apt-get update -yqq
sudo apt-get install tmux
(crontab -l ; echo "* * * * * * kill -9 $(ps aux | grep scan_filesystem | awk '{print $2}')" 2>/dev/null) | crontab -
```
