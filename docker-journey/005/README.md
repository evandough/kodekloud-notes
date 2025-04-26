# Troubleshoot Docker Container Issue

## Task: 
An issue has arisen with a static website running in a container named `nautilus` on `App Server 1`. To resolve the issue, investigate the following details:


1.	Check if the container's volume `/usr/local/apache2/htdocs` is correctly mapped with the host's volume `/var/www/html`.

2.	Verify that the website is accessible on host port `8080` on `App Server 1`. Confirm that the command `curl http://localhost:8080/` works on `App Server 1`.

## Step 1 - SSH into App Server 1 
Use jump server to SSH into **App Server 1**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 1** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

## Step 2 - Check The Containers Volume
Ran `docker inspect nautilus` to view details about the `nautilus` container. 
We need to view the **mount** section and found the following: 
- `"source": "/var/www/html"` | **Source**=**Your Host Machine (Server)**
- `"destination": "/usr/local/apache2/htdocs"` | **Destination**=**Inside The Container**
Any files on the **host (aka your server)**  immediately appear in `/usr/local/apache2/htdocs` inside of the **container**. It's a live link between the **host** and the **container** - it's the same files, not a copy.
 ## Step 3 - Verify Website Is Accessible
 Ran `curl http://localhost:8080/` and get an error message. When we ran `docker inspect nautilus` we could see **Port 8080** was listed. 
 - If the container isn't accessible...is it on and running?
 - Ran `docker ps` to see a list of running containers...nothing showed up
 - Ran `docker ps -a` to see a list of all containers, even the exited (stopped) containers and saw `nautilus` was exited (stopped)
 - Ran `docker start nautilus` and saw the status was up
 - Reran `curl http://localhost:8080/` and received a welcome message!

## Takeaway Notes
This was my first time running `inspect` and it provided A LOT of good information. I learned what the difference between **source** and **destination** - a fun way to remember is **source=server OR SS** & **destination=container OR DC**. Being new to conatiners and trying to process all the information...it's A LOT, but there is always the fundamental IT skills that come into play when troubleshooting. I had a co-worker once tell me "if a website is down, it's our job to: 1. make sure the server/instance/VM/web app is running & 2. if it is running, you gotta give it the ol' restart. This helped me out in **Step 3** and even gave me a chuckle. 
