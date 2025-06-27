# Create Security Group Using Terraform

## Task: 
Within the Stratos DC, the Nautilus storage server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `mariyam` has requested a copy of their data stored in `/data/mariyam`. The System Admin team has provided the following steps to fulfill this request:



a. Create a compressed archive named `mariyam.tar.g`z of the `/data/mariyam directory`.

b. Transfer the archive to the `/home` directory on the Storage Server.				

## Step 1 - SSH into the `storage server`

## Step 2 - Ran the following commands
1. `sudo tar -czvf /tmp/mariyam.tar.gz /data/mariyam` 
- This creates a compressed backup file of a folder
- `tar` = backup/archive tool
- `-czvf` = four instructions:
  - `c` = create a new archive
  - `z` = zip it
  - `v` = verbose (show what's happening)
  - `f` = file (filename)
- `/tmp/mariyam.tar.gz` = name and location of the backup file to create
- `/data/mariyam` = the folder we want to backup
- We're taking the file/folder and putting it in a ZIP file, and saving the ZIP file somewhere else
2. `sudo mv /tmp/mariyam.tar.gz /home/`
- Transfers the archive to the `/home` directory
