# Delete Docker Container 

## Task: 
A container named `kke-container` was created by one of the Nautilus project developers on `App Server 3`. It was solely for testing purposes and now requires deletion. Execute the following task: 

Delete the kke-container on `App Server 3` in `Stratos DC`.

### Step 1. 
Use jump server to SSH into **App Server 3**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 3** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

### Step 2. 
To list the containers I ran `docker container ls` and was able to view `kke-container`
- This command lists all **Docker** containers

### Step 3. 
Ran `docker container rm kke-container`
- This command deletes the container

Couldn't remove, becuase it's running, so ran `docker container stop kke-container`
- This command stops the **Docker** container

I reran `docker container rm kke-container`

### Step 4. 
Celebrate for a job well done.
