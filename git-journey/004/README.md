# Update Git Repository with Sample HTML File

## Task: 
The Nautilus development team has initiated a new project development, establishing various Git repositories to manage each project's source code. Recently, a repository named `/opt/ecommerce.git` was created. The team has provided a sample `index.html` file located on the `jump host` under the `/tmp directory`. This repository has been cloned to `/usr/src/kodekloudrepos` on the `storage server` in the `Stratos DC`.



1. Copy the sample `index.html` file from the `jump host` to the `storage server` placing it within the cloned repository at `/usr/src/kodekloudrepos/ecommerce`.

2. Add and commit the file to the repository.

3. Push the changes to the `master` branch.

## Step 1 - Copy the sample `index.html` file from the `jump host` to the `storage server`
Ran `scp path/to/index.html natasha@ststore01:/home/natasha/`
- `scp` means **secure copy protocol**. A command-line utility used to securely transfer files between sumputers over an SSH connection
  - This securely copies `index.html` to the **storage server**
 
## Step 2 - Place `index.html` into `/usr/src/kodekloudrepos/ecommerce`
Ran `sudo mv path/to/index.html /usr/src/kodekloudrepos/ecommerce`
<br></br>
`cd` into `/usr/src/kodekloudrepos/ecommerce`
<br></br>
Ran `git config --global --add  safe.directory /usr/src/kodekloudrepos/ecommerce`
- This tells Git that a specific directory is safe to use even if it's owned by another user or has unusual permsissions
- `--global` adds the setting to your user's Git config
- `--add` allows you to add multiples safe directories
- `safe.directory` is the config entry Git checks to allow operations in that directory

## Step 3 - Add and commit the file to the repository
Ran these command to add, commit, and push `index.html` into the repo: 
- `sudo git add index.html`	
- `sudo git commit -m "Added index.html file"`
- `sudo git push origin master`
