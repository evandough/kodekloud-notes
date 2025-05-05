# Service User Creation without Home Directory

## Task: 
In response to the latest tool implementation at `xFusionCorp Industries`, the system admins require the creation of a service user account. Here are the specifics:

Create a user named `ammar` in `App Server 2` without a home directory.

## Step 1 - SSH into App Server 1 
Use jump server to SSH into **App Server 1**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 1** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Create a user named `ammar` in `App Server 2` without a home directory
- By default, **Linux** creates a user in the home directory at `/home/username`. 
- Ran `sudo useradd -M ammar`  
  - `-M` = without a home directory
  - `useradd` = creates the user `ammar` 

## Step 3 - VERIFY!
Verified by running `id ammar`
- This displays the user ID (UID), group ID (GID), and group memberships for the specified user
