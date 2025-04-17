# Install Docker Packages and Start Docker Service

## Task: 
Install `docker-ce` & `docker compose` onto `Application Server 2` and initiate

## Step 1. 
Use jump server to SSH into **App Server 2**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 2** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2. 
We need to find which Linux OS we have by running `cat /etc/os-release`
- `cat`: Short for “concatenate” — here it just prints the contents of a file.
- `/etc/os-release`: A standard file on most Linux systems that contains OS identification data.

I used this link to download `docker-ce` and follwed the steps- https://docs.docker.com/engine/install/centos/#install-using-the-repository

## Step 3. 
Verified and validated Docker was initiated successfully 
