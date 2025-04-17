# Custom Apache User Setup

## Task: 
In response to heightened security concerns, the **xFusionCorp Industries** security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. 
<br></br>
Your task is to create a custom Apache user according to the outlined specifications:

- A. Create a user named john on App server 1 within the Stratos Datacenter.
- B. Assign a unique UID 1843 and designate the home directory as /var/www/john

## Step 1. 
Use the jump server to SSH into **App server 1**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 1** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2. 
Add `john` as a user with a **unique UID 1843** and designate the home directory as **/var/www/john**
- Run `sudo adduser --uid 1843 --home /var/www/john john`
  - `adduser` adds a new user
  - `--uid 1843` creates a unique UID for the new user
  - `--home /var/www/john` creates this user in the home directory
  - at the very end you'll see `john`, and this is the name of the new user 

## Step 3. 
- Verify john is a user by running `ls -la /var/www/john' (checking the home directory)
  - `ls` stands for list all files   
- Verify john is a user by running `id john' 
