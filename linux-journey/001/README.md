# Custom Apache User Setup

## Task: 
In response to heightened security concerns, the **xFusionCorp Industries** security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. 
<br></br>
Your task is to create a custom Apache user according to the outlined specifications:

- A. Create a user named john on App server 1 within the Stratos Datacenter.
- B. Assign a unique UID 1843 and designate the home directory as /var/www/john

### Step 1. 
Use the jump server to SSH into **App server 1**
- Run `ssh username@IP` to SSH into **App server 1**

## Step 2. 
Add `john` as a user with a **unique UID 1843** and designate the home directory as **/var/www/john**
- Run `sudo adduser --uid 1843 --home /var/www/john john`

## Step 3. 
- Verify john is a user by running `ls -la /var/www/john' (checking the home directory)
- Verify john is a user by running `id john' 
