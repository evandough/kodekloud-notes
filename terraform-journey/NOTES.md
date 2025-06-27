# Helpful Commands

- `terraform fmt` - format and standardize the layout of Terraform configuration files
- `terraform init` - Get your tools ready = Downloads everything Terraform needs to work with your cloud provider
- `terraform plan` - Show me the blueprint = Shows you exactly what will be created/changed/deleted
- `terraform apply` - Build it = This is where real stuff gets created in your cloud environment
- `tar` = backup/archive tool
  - `-czvf` = four instructions:
    - `c` = create a new archive
    - `z` = zip it
    - `v` = verbose (show what's happening)
    - `f` = file (filename)
      - ex. `sudo tar -czvf /tmp/mariyam.tar.gz /data/mariyam`
        -  `/tmp/mariyam.tar.gz` = name and location of the backup file to create
        - `/data/mariyam` = the folder we want to backup
          - We're taking the file/folder and putting it in a ZIP file, and saving the ZIP file somewhere else
