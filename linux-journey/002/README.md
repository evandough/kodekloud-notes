# Group Creation and User Assignment

## Task: 
The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:

- a. Create a group named `nautilus_noc` across all App servers within the `Stratos Datacenter`.
- b. Add the user `kano` into the `nautilus_noc` group on all App servers. If the user doesn't exist, create it as well.

## Attempt #1
- created group using `sudo groupadd nautilus_noc`

- Verified group by running `grep nautilus_noc /etc/group`

- Added `kano` as a user using `sudo adduser kano`
- Added `kano` to the group by running `sudo usermod -aG nautilus_noc kano`
- Verified kano by running `id kano'

**DIDN'T WORK - ERROR MESSAGE: - USER 'KANO' DOES NOT EXIST ON APP SERVER 1**

# REFLECTION - I need to SSH into each App Server within the `Stratos Datacenter` to add KANO to successfully complete the task

# Attempt #2
## Task: 
The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:
- a. Create a group named `nautilus_admin_users` across all App servers within the `Stratos Datacenter`.
- b. Add the user `rajesh` into the `nautilus_admin_users` group on all App servers. If the user doesn't exist, create it as well.

## Step 1 - SSH into ALL App Servers
Use jump server to SSH into **App Server 1, 2, & 3**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 3** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.
<br></br>
Type `yes` to connect and then type in the password - BOOM! We're in.

## Step 2 - Create a group named `nautilus_admin_users` across all App servers
1. Created the group using the command `sudo groupadd nautilus_admin_users`
   - `group add` creates the group
2. Verified group by running `grep nautilus_admin_users /etc/group`
   - `grep` stands for `g/re/p` → **globally search a regular expression and print**
  
## Step 3 - Add the user `rajesh` into the `nautilus_admin_users` group on all App servers. If the user doesn't exist, create it as well.

1. I wanted to see if Rajesh was a current user or if we needed to create Rajesh as a user
   - I ran `id rajesh' and got `id: ‘rajesh’: no such user`...let's get Rajesh added as a user to the `nautilus_admin_users` group on all App servers
2. Ran `sudo adduser --groups nautilus_admin_users rajesh`
   - This command adds the user `rajesh` to the `nautilus_admin_users` group
4. Verified Rajesh was added as a user to the `nautilus_admin_users` group by running:
   - `id rajesh` and got back the `uid`, `gid`, and `groups`
