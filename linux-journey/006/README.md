# Linux User Data Transfer

## Task: 
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus `App Server 1` at the `/home/usersdata` location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:

Locate all files (excluding directories) owned by user `mark` within the `/home/usersdata` directory on `App Server 1`. Copy these files while preserving the directory structure to the `/beta` directory.

## Step 1 - SSH into App Server 1 
Use jump server to SSH into **App Server 1**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 1** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Locate all files (excluding directories) owned by user `mark` within the `/home/usersdata` directory on `App Server 1`
Ran `find /home/usersdata -type f -user mark`
	- `/home/usersdata`: directory to search
	- `-type f`: only files
	- `-user mark`: user `mark`

## Step 3 - Copy these files while preserving the directory structure to the `/beta` directory
Ran `find /home/usersdata -type f -user mark -exec cp --parents {} /beta \;`
- `find /home/usersdata`: finds the directory
- `-type f`: restricts search to regular files only
- `-user mark`: finds files owned by `mark`
- `-exec ... \;`: this tells `find` to execute a command on each file it finds
- `cp --parents {} /beta`: 
  - copies (`cp`)
  - `--parents`: tells `cp` to preserve the directory structure, i.e. puts the file path onto `beta` 
    ex. `/home/your/path` to `beta/home/your/path`
  - `{}` is a placeholder for each file found by `find`
  - `\;` ends the `-exec` clause
  
## Step 4 - VERIFY
Ran `find /beta -type f`
- This will list all files in the `/beta` folder to show the correct path








