# Delete Git Branch

## Task: 
The Nautilus developers are engaged in active development on one of the project repositories located at /usr/src/kodekloudrepos/ecommerce. During testing, several test branches were created, and now they require cleanup. Here are the requirements provided to the DevOps team:



On the Storage server in Stratos DC, delete a branch named xfusioncorp_ecommerce from the /usr/src/kodekloudrepos/ecommerce Git repository.

## Step 1 - Copy the sample `index.html` file from the `jump host` to the `storage server`
Ran `scp path/to/index.html natasha@ststore01:/home/natasha/`
- `scp` means **secure copy protocol**. A command-line utility used to securely transfer files between sumputers over an SSH connection
  - This securely copies `index.html` to the **storage server**
 
## Step 2 - `cd` into the correct repo

## Step 3 - Ran the following to delete branch
`git branch -d xfusioncorp_ecommerce`
	can't delete
		git worktree list and I see that I'm in the branch that needs to be removed, so I `git checkout master`
			`sudo git branch -d xfusioncorp_ecommerce`

## Step 4 - Verify   
Verify by running `git branch` and no longer seeing the branch
