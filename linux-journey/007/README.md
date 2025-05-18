# Secure Root SSH Access

## Task: 
Following security audits, the `xFusionCorp Industries` security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the `Stratos Datacenter`.

## Step 1 - SSH into All App Servers  
Use jump server to SSH into **All App Servers**
- Ran `ssh username@IP`
  - This command securely connects to **All App Servers** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - `cd` into the Root SSH & then `cd` into `etc/ssh/`
Ran `cd ..` till I reached the root
- Ran `cd etc/ssh/`

## Step 3 - Edited the `sshd_config`
Ran `sudo vi sshd_config`
- Press `i` to insert & change `PermitRootLogin` to `no` instead of yes and then save by hitting `esc` and typing `:wq`
  - **What is `sshd_config`?**
    - In Linux, /etc/ssh/sshd_config is the main configuration file for the OpenSSH server daemon (sshd). This file controls various aspects of the SSH server's behavior, including encryption, authentication, and logging.
  - **What does `:wq` do?**
    - `:` - enters command mode
    - `w` - write the file
    - `q` - quit the editor
      - Essentially `:wq` = save and exit  

## Step 4 - Restart SSH Service
Restart SSH Service by running `sudo systemctl restart sshd`
- **Why restart?**
  - Changes don't take effect automatically. The SSH daemon (`sshd`) needs to reload its config.

 ## Step 5 - VERIFY
 Verify changes by running `sudo sshd -T | grep permitrootlogin` and got `permitrootlogin no`
 - **What does `sudo sshd -T | grep permitrootlogin` do?**
   - `sudo` = root privileges
   - `sshd -T` = tells ssh daemon to dump effective config to show all active settings
   - `| grep permitrootlogin` = this filters the output to show only the line that includes permitrootlogin
     - `grep` searches for patterns in files 
