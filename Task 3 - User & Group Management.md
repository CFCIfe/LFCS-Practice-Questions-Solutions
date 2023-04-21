### Linux administrators are responsible for the creation, deletion, and the modification of groups, as well as the group membership. Complete the following tasks to demonstrate your ability to create and manage groups and group membership.

#### A. Create the computestream group. Create a computestream folder in /exam/ and make the computestream group the owner of the /exam/computestream folder.


#### Solution

```
#!/bin/bash
sudo groupadd computestream
mkdir -p /exam/computestream
sudo chgrp --silent computestream /exam/computestream
```
---

#### B. Create a candidate user account with the password cert456. Modify the sudo configuration to let the candidate account access root privileges with no password prompt.

#### Solution

``` 
#!/bin/bash
# Create A new user 'candidate'
sudo useradd -p cert456 candidate
# Give sudo priviledge with no password prompt
echo "candidate ALL=(ALL:ALL) NOPASSWD:ALL" | sudo tee -a /etc/sudoers
```

---

#### C. Configure the system so that an empty NEWS file is automatically created in the home directory of any new user

#### Solution

The /etc/skel directory holds the default folders/files that are created for new users in their home directory. It is a skeleton and is defined in the /etc/default/useradd file under the skel option.

``` touch /etc/skel/NEWS ```

---

#### D. Create a group called students and a new user account with the following attributes:
#### ● Username is harry.
#### ● Password is magic.
#### ● This user’s home directory is defined as /home/school/harry/.
#### ● This new user is a member of the existing students group.
#### ● The /home/school/harry

#### 
