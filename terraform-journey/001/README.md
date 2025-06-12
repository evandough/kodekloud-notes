# Create Key Pair Using Terraform

## Task: 
1. Create a `key pair` with provided naming convention.
2. Key pair type must be `rsa`.
3. The private key file should be saved under `/fiel/path/provided`.

## Step 1 - `cd` into the Terraform working directory
 
## Step 2 - Create a `main.tf` to create an AWS Key Pair Configuration
I followed the Terraform documentation on crating a Key Pair: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/key_pair

## Step 3 - Ran the appropriate Terraform commands
Once the `main.tf` was created and saved, I ran the following commands: 
- `terraform init`
  - Creates a `.terraform` folder with all the necessary files
  - Initializes the backend
  - Essentially, setups up your Terraform workspace
- `terraform plan`
  - Shows you the preview of changes before making them
- `terraform apply`
  -  Creates/modifies/destorys your infrastructure
  -  Updates the Terraform state file 

