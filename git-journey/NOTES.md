# Git Command Syntax
`git <command> [options] [arguments]`

# Helpful Commands
- `git add` - stages your changes
- `git commit` - saves a snapshot or records your changes
  - What to add a message on what you're commiting? add git commit -m "your message here"`
- `git push` - sends your commits from your local repo to a remote(i.e., GitHub) 
- `git clone` - clones the Git repo
- `scp` - **secure copy protocol**. A command-line utility used to securely transfer files between sumputers over an SSH connection
- `git config --global --add  safe.directory /path/to/repo` - This tells Git that a specific directory is safe to use even if it's owned by another user or has unusual permsissions
  - `--global` adds the setting to your user's Git config
  - `--add` allows you to add multiples safe directories
  - `safe.directory` is the config entry Git checks to allow operations in that directory
