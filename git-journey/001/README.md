# Set Up Git Repository on Storage Server

## Task: 
The Nautilus development team has provided requirements to the DevOps team for a new application development project, specifically requesting the establishment of a Git repository. Follow the instructions below to create the Git repository on the `Storage server` in the Stratos DC:

Utilize `yum` to install the `git` package on the `Storage Server`.

Create a bare repository named `/opt/apps.git` (ensure exact name usage).

## Step 1 - SSH into the Storage Server  
Use jump server to SSH into the **Storage Server**
- Ran `ssh username@IP`
  - This command securely connects to **Storage Server** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network
 
## Step 2 - Install `git` using `yum`
I Google'd [how to install Git onto Linux](https://git-scm.com/book/it/v2/Per-Iniziare-Installing-Git) and ran `yum install git` and received this error message: `Error: This command has to be run with superuser privileges (under the root user on most systems).`
Ran `sudo yum install git`. I was asked if the install was ok and typed `y`. 
- What does `sudo yum install git` do?
  - `yum` is a tool that helps you install, update, and remove software

## Step 3 - Create a bare repository name `/opt/apps.git`
Found a StackOverflow on creating a bare repo and ran `git init --bare /opt/apps.git`. I ran into another permission issue, so I ran `sudo git init --bare /opt/apps.git`. RECEIVED A SUCCESS MESSAGE!
- What does `git init --bare /opt/apps.git` do?
  - `git init` initializes a new Git repo
  - `--bar` tells Git to make a bare repo
    - Does NOT have a working directory
    - Is used as a central or remote repo (like on a server) for sharing where others will push/pull  

## Step 4 - VERIFY
I ran `ls /opt/apps.git` and received an output showing it was successful. 
- What does `ls /opt/apps.git` do?
  - Lists the contents of the `/opt/apps.git` repo 

