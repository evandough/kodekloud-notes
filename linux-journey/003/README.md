# Linux User Setup with Non-Interactive Shell

## Task: 
To accommodate the backup agent tool's specifications, the system admin team at `xFusionCorp Industries` requires the creation of a user with a non-interactive shell. Here's your task:

Create a user named `jim` with a non-interactive shell on `App Server 1`.

## Step 1 - SSH into App Server 1 
Use jump server to SSH into **App Server 1**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 1** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Add `jim` as a user with a non-interactive shell on `App Server 1`.
First of all, what is non-interactive shell?
- A non-interactive environment is one where the shell or process does not expect or allow user input during its execution.
Ran `sudo useradd -s /usr/sbin/nologin jim`
- This command adds `jim` as a user
- `user add` = creates the user
- `-s /usr/sbin/nologin` = assigns a shell that denies login (non-interactive)
- `jim` = the user to create

## Step 3 - VERIFY!
Verified with `getent passwd jim`
- `getent`= get entries, to fetch information from databases
- `getent passwd` = will show all user entries that are available on the system
