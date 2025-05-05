# Linux Notes & Resources

# Basic Linux Command Syntax
`command [options] [arguments]`

	- command – The name of the program or built-in shell command.

	- [options] – Modifiers that change the behavior of the command (usually prefixed with - or --).

	- [arguments] – Targets of the command (files, directories, users, etc.).
 
# Helpful Commands
- `sudo` - Means "superuser do" | temporarily gives you administrator (root) privileges to run a specific command. This is essential because many system-level tasks — like installing software, changing system settings, or adding users require root access
- `echo` - This command prints text to the termial or writes to a file
- `nano` - Opens a file in the Nano text editor
  - ex. `nano wp.config` opens the `wp.config` text editor   
- `vi` - Opens a file in the Vi text editor
- `grep` - Searches for patterns in files
- `find` - Searches for files and directories in a directory hierarchy
- `chmod` - Changes file permissions
- `chown` - Changes the owner of a file or directory
- `locate` - Finda the location of files
- `du` - Displays disk usage of files and directories
- `df` - Displays available disk space
- `ls` - Lists files and directories
- `cd` - Changes the current directory
  - ex. `cd plugins` changes directory to `plugins` directory. Need to go back a directory? Run `cd ..`  
- `pwd` - Prints the current working directory
- `cp` - copies files or directories
  - ex. `cp cool.stuff.gpg` copies `cool.stuff.gpg`
- `mv` - Moves or renames files or directories
  - ex. `mv cool-plugin old-cool-plugin` renames `cool-plugin` as `old-cool-plugin`
- `rm` - Removes files or directories
  - ex. `rm cool-plugin` removes `cool-plugin` file
- `mkdir` - Creates new directory
- `rmdir` -Removes an empty directory
- `touch` - Creates an empty file or updates the temestamp of a file
- `cat` -concatenates (links things together in a chain or series) and displays the content of files
- `top` - Shows realtime system processes and resource usage
- `ps` - Displays currently running processes
- `kill` - Terminates processes by proccess ID (PID)
- `ping` - Sends network packets to test connectivity to a host
- `ifconfig` - Configures network interfaces
- `wget` - Downloads files from the internet
- `curl` - Transfers data to or from a server
- `tar` - Archives files into a single file or extracts from an archive
- `zip` - Compresses files into a .zip archive
- `whoami` - Displays the current logged in user
- `hostname` - Displays or sets the system hostname
- `df` - Reports file system disk space usage
- `uptime` - Shows how long the system has been running
- `history` - Displays command history
- `clear` - Clears the terminal screen
- `reboot` - Restarts the system
- `shutdown` - Shuts down the system
- `service` - Manages system services
- `systemctl` - Controls the systemd system and service
- `useradd -M` - creates a user without a home directory
  - ex. `sudo useradd -M ammar` = add the user ammar without a home directory 
