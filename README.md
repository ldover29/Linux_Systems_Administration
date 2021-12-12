# Linux_Systems_Administration
The basics of IT system administration

# Scenario
You acted as system administrator in order to troubleshoot a malfunctioning server.

The senior administrator was quite pleased with your work. Now, they would like you to prepare another server to replace this server. You are tasked with completing the steps below to prepare a new server.

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

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/900c4cfdf6c43fe5bc535b0b0526ec052cd6dfa2/images/step%203%20-%201%20sudo%20addgroup%20engineers.jpg)

**2. Add users sam, joe, amy, and sara to the managed group.**

- Command to add users to engineers group (include all four users): 

**sudo usermod -aG engineers sam**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/f00324e36b51e18ee155880b1d9b1cd4832adf2a/images/step%203%20-%202%20%20sudo%20usermod%20-ag%20engineers%20sam.jpg)

**sudo usermod -aG engineers joe**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/f00324e36b51e18ee155880b1d9b1cd4832adf2a/images/step%203%20-%202%20%20sudo%20usermod%20-ag%20engineers%20joe.jpg)

**sudo usermod -aG engineers amy**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/f00324e36b51e18ee155880b1d9b1cd4832adf2a/images/step%203%20-%202%20%20sudo%20usermod%20-ag%20engineers%20amy.jpg)

**sudo usermod -aG engineers sara**

**3. Create a shared folder for this group at /home/engineers.**

- Command to create the shared folder: **sudo chmod 777 /home/engineers**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/5f2010f7734930ec1886957e40d3198ace2a5276/images/step%203%20-%203%20%20sudo%20chmod%20-777.jpg)

**4. Change ownership on the new engineers' shared folder to the engineers group.**

- Command to change ownership of engineer's shared folder to engineer group: **sudo chown :engineers /home/engineers**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/5f2010f7734930ec1886957e40d3198ace2a5276/images/step%203%20-%204%20%20sudo%20chown.jpg)

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/5f2010f7734930ec1886957e40d3198ace2a5276/images/step%203%20-%204%20%20sudo%20chown%202.jpg)

# Step 4: Lynis Auditing

1. Command to install Lynis: **sudo apt -y install lynis**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/9b061fce6d51e88d136969942bd47c2aa6dfc9e1/images/Step%204%20-%201.jpg)

2. Command to see documentation and instructions: **man lynis**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/9b061fce6d51e88d136969942bd47c2aa6dfc9e1/images/Step%204%20-%202.jpg)

3. Command to run an audit: **sudo lynis audit system**

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/9b061fce6d51e88d136969942bd47c2aa6dfc9e1/images/Step%204%20-%202b.jpg)

4. Provide a report from the Lynis output on what can be done to harden the system.

Screenshot of report output: 

![name-of-you-image](https://github.com/ldover29/Linux_Systems_Administration/blob/9b061fce6d51e88d136969942bd47c2aa6dfc9e1/images/Step%204%20-%204.jpg)
