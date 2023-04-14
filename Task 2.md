### Operation of Running System.
---
Create a bash shell script named certscript.sh under /home/student/apps/.

1. Make sure the script can be invoked as
./certscript.sh.
2. The first line of output from the script should consist of the name of the user who invoked it.
3. The second line of output should contain the IP address of the default gateway.

---
### Solution

- touch /home/student/apps/certscript.sh
- chmod +x /home/student/apps/certscript.sh
- nano /home/student/apps/certscript.sh
  - Type the following into the file
    ```
    #!/bin/bash
    echo $USER
    echo $(ip route show default| awk'{print $3; exit}')
    ```