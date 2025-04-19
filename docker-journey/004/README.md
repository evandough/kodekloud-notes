# Copy File to Docker Container 

## Task: 
The Nautilus DevOps team possesses confidential data on `App Server 2` in the `Stratos Datacenter`. A container named `ubuntu_latest` is running on the same server.

Copy an encrypted file `/tmp/nautilus.txt.gpg` from the docker host to the `ubuntu_latest` container located at `/usr/src/`. Ensure the file is not modified during this operation.

## Step 1 - SSH into App Server 2 
Use jump server to SSH into **App Server 2**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 2** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Verify That A Container Named `ubuntu_latest` Is Running On The App Server
Ran `docker container ls` to view the container and I can see `ubuntu_latest`

## Step 3 - Copy The Encrypted File From The Docker Host To The `ubuntu_latest` Container Located At `/usr/src/`
- I originally ran `docker COMMAND` to get a list of commands and spotted `cp`
  - The `cp` command copies files between host and container
- I ran `docker cp /tmp/nautilus.txt.gpg ubuntu_latest:/usr/src/`
  - **What this command does:**
  - `cp` copies files between host and container - this will copy the encrypted file `/tmp/nautilus.txt.gpg` to the container`ubuntu_lates` in the `/usr/src/` directory
  - 

## Step 4 - Verification! 
I ran `docker exec -it ubuntu_latest ls -l /usr/src/` to verify the file was copied and moved succesfully
- `docker exec` executes the command within a docker container
- `-it` let's you see and interact with the container
- `ubuntu_latest` is the container we're checking to ensure the files are copied to
- `ls -l /usr/src/` lists the files and looks specifically at `/usr/src/`

## Takeaway Notes
Research was done on the proper command to execute because I've had experience with the `mv` command to rename files within a WordPress instance to check plugins, but I've never had to copy a file and move it. 
