# Docker Notes & Resources

# Docker Works Like This
`docker <COMMAND> [OPTIONS]`

# Helpful Commands
- `docker --help` - To get a list of Docker commands
- `docker cp` - Copies files between host and container
  - ex. `docker cp /tmp/nautilus.txt.gpg` copies the gpg file `/tmp/nautilus.txt.gpg`
- `docker rm` - Removes (deletes) containers
  - ex. `docker container rm kke-container` deletes the `kke-container`
- `docker images` - Shows the containers
- `docker run` - Creates a new container from a Docker image
  - ex. `docker run --name nginx_2` creates a container named `nginx_2`
- `docker start` - Starts the docker image
  - ex. `docker start nginx_2` starts the docker image `nginx_2`
- `docker inspect` - provides detailed, low-level information
  - ex. `docker inspect [container-name]` provides various information about the container 
- `docker ps` - shows your a list of running containers
- `docker ps -a` - shows your a list of all containers, even the exited (stopped) containers 
