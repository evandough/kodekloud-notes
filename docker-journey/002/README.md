# Deploy Nginx Container on Application Server 

## Task: 
On `Application Server 2` create a container named `nginx_2` using the `nginx` image with the `alpine` tag. Ensure container is in a `running` state.

### Step 1. 
Use jump server to SSH into **App Server 2**
- Ran `ssh username@IP`
  - This command securely connects to **App Server 2** via SSH
  - A jump server (also known as a jump host, bastion host, or jump box) is a special-purpose server used to manage access to devices in a separate security zone, typically within a private network or DMZ (demilitarized zone). It's like a gateway that administrators use to "jump" into more secure parts of the network.

### Step 2. 
View the docker images by running `docker images`

To create a container I ran `docker run --name nginx_2 nginx:alpine`
- `docker run` creates a new container from a **Docker** image
- `--name nginx_2` names the new container **nginx_2**
- `nginx:alpine` is the tag that is associated with the **nginx image**

### Step 3. 
We need to verify the container is running
   
- ran `docker images` and saw the container we created, but saw it wasn't running
  - this command shows your current **Docker images** 
- ran `docker start nginx_2`
  - this command starts the **Docker image**
