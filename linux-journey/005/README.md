# Temporary User Setup With Expiry

## Task: 
As part of the temporary assignment to the `Nautilu`s project, a developer named `kirsty` requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

Create a user named `kirsty` on `App Server 3` in Stratos Datacenter. Set the expiry date to `2024-03-28`, ensuring the user is created in lowercase as per standard protocol.

## Step 1 - SSH into App Server 3 
Use jump server to SSH into **App Server 3**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 3** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Create a user named `kirsty` on `App Server 3`
Ran `sudo useradd -e 2024-03-28 kirsty`
- input password to verify you have access and "with great power comes great responsibility"
- `-e` means **expiry date**

## Step 3 - VERIFY
Ran `sudo chage -l kirsty`
- Account expires = Mar 28, 2024
`chage` means **view and modify user account aging information**
