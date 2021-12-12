# Linux_Systems_Administration
The basics of IT system administration

# Step 1: Ensure/Double Check Permissions on Sensitive Files

**1. Permissions on /etc/shadow should allow only root read and write access.**

- Command to inspect permissions: **ls -l shadow**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/ea6119e06562f4d7f240ab6e0aee9ee97384be19/images/1%20ls%20-l%20shadow.jpg)

- Command to set permissions (if needed): **n/a**

**2. Permissions on /etc/gshadow should allow only root read and write access.**

- Command to inspect permissions: **ls -l gshadow**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/2%20ls-%20l%20gshadow.jpg)

- Command to set permissions (if needed): **n/a**

**3. Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.**

- Command to inspect permissions: **ls -l group**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/3%20ls%20-l%20group.jpg)

- Command to set permissions (if needed): **n/a**

**4. Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.**

- Command to inspect permissions: **ls -l passwd**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/4%20ls%20-l%20passwd.jpg)

- Command to set permissions (if needed): **n/a**

# Step 2: Create User Accounts

**1. Add user accounts for sam, joe, amy, sara, and admin.**

- Command to add each user account (include all five users):

**sudo adduser sam**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/step%202%20-%201%20sudo%20adduser%20sam.jpg)

**sudo adduser joe**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/step%202%20-%201%20sudo%20adduser%20joe.jpg)

**sudo adduser amy**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/step%202%20-%201%20sudo%20adduser%20amy.jpg)

**sudo adduser sara**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/step%202%20-%201%20sudo%20adduser%20sara.jpg)

**sudo adduser admin**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/1c8d31b69c858ea2f586f3e6fb62a3af836d7e64/images/step%202%20-%201%20sudo%20adduser%20admin.jpg)

**2. Ensure that only the admin has general sudo access.**

- Command to add admin to the sudo group: **sudo usermod -aG sudo admin**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/dc21735d0e2aa51d925562b1d27c033f2bb6712a/images/step%202%20-%202%20sudo%20usermod%20-ag%20admin.jpg)

# Step 3: Create User Group and Collaborative Folder

**1. Add an engineers group to the system.**

- Command to add group: **sudo addgroup engineers**

**2. Add users sam, joe, amy, and sara to the managed group.**

- Command to add users to engineers group (include all four users): 

**sudo usermod -aG engineers sam**

**sudo usermod -aG engineers joe**

**sudo usermod -aG engineers amy**

**sudo usermod -aG engineers sara**

**3. Create a shared folder for this group at /home/engineers.**

- Command to create the shared folder: **sudo chmod 777 /home/engineers**

**4. Change ownership on the new engineers' shared folder to the engineers group.**

- Command to change ownership of engineer's shared folder to engineer group: **sudo chown :engineers /home/engineers**

# Step 4: Lynis Auditing

1. Command to install Lynis: **sudo apt -y install lynis**

2. Command to see documentation and instructions: **man lynis**

3. Command to run an audit: **sudo lynis audit system**

4. Provide a report from the Lynis output on what can be done to harden the system.

Screenshot of report output: 
