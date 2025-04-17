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

### REFLECTION - I need to SSH into each App Server within the `Stratos Datacenter` to add KANO to successfully complete the task

## Attempt #2
