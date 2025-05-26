# Clone Git Repository on Storage Server

## Task: 
The DevOps team established a new Git repository last week, which remains unused at present. However, the Nautilus application development team now requires a copy of this repository on the `Storage Server` in the Stratos DC. Follow the provided details to clone the repository:

1. The repository to be cloned is located at `/opt/media.git`

2. Clone this Git repository to the `/usr/src/kodekloudrepos` directory. Ensure no modifications are made to the repository during the cloning process.

## Step 1 - SSH into the Storage Server  
Use jump server to SSH into the **Storage Server**
- Ran `ssh username@IP`
  - This command securely connects to **Storage Server** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network
 
## Step 2 - Clone the `/opt/media.git` repo to `/usr/src/kodekloudrepos` directory
Before we can clone the repo to another directory, **you have to `cd` into the directory you want the repo to be in.** So you'll have to `cd` into the `/usr/src/kodekloudrepos` directory. Based off of the Linux command syntax I ran `git clone /opt/media.git /usr/src/kodedkloudrepos`. Ran into a permission issue so I modified the command with `sudo git clone /opt/media.git /usr/src/kodedkloudrepos`. Added the password and **BOOM!** I cloned the repo. 

## Step 3 - VERIFY!
`cd` into the /usr/src/kodekloudrepos` directory and ran a `sudo git status` and got a message that I was on the main branch with no commits yet. 
