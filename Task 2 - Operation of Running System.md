### Operation of Running System.

A. Create a bash shell script named certscript.sh under /home/student/apps/.

1. Make sure the script can be invoked as ./certscript.sh.
2. The first line of output from the script should consist of the name of the user who invoked it.
3. The second line of output should contain the IP address of the default gateway.

---
### Solution

- ```touch /home/student/apps/certscript.sh```
- ```chmod +x /home/student/apps/certscript.sh```
- 
```
nano /home/student/apps/certscript.sh
#Type the following into the file
  ``
  #!/bin/bash
  echo $USER
  echo $(ip route show default| awk'{print $3; exit}')
  ``
```
---

### Operation of Running System 2.

1. Install the tmux package on your system.
2. Create a cron job that kills all processes named scan_filesystem which is owned by root, every minute.

### Solution

- ``` touch install.sh && chmod +x installl.sh ```
Add the following to the running_sys.sh file
```
#!/bin/bash
sudo apt-get install -qq && sudo apt-get update -yqq
sudo apt-get install tmux
```
- 
```
  sudo crontab -e
  #add the following contents
  * * * * * * kill -9 $(ps aux | grep scan_filesystem | awk '{print $2}')" 2>/dev/null
```