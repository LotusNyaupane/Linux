# Linux
# Account Setup

In the first step, I have created a Microsoft Azsure account using our university email address. Then, my microsoft azsure account is successfully created and I have recevied $100 worth of credit which helps me to purchase different types of useful learning environment.

# Create Virtual Machine
I have created a virtual machine where I can learn and do some projects for this course.
Then, I named the machine "lab-robotics" and then I have select the no infrastructure redundancy required option and Trusted launch virtual machines security type.
I choosed Ubuntu Server 24.04 LTS - x64 Gen2 server and B series version 2 which is Standard_B21s_v2.
After completing all the steps, I got a key and I have selected the connect option and choose the native ssh option.
There is a copy and execute SSH command button, I have pasted the key which I have got earlier.
Then open the windows powershell and paste the link generated link there and I reached in the Linux virtual machine.
It help us to use Linux in windows laptop without installing it.
# Linking my GitHub account to my HAMK email
I created a new repository named "Linux" for the assignment.
Then I linked my HAMK email as a secondary mail for version control.

# screenshot
![alt text](<Screenshot 2025-01-23 005637.png>)
 ![alt text](<Screenshot 2025-01-19 201436.png>)

# Assignment 3 User Management and File System access

# Creating Users Tupu (Using) To create the user tupu, use the following command: 
         sudo adduser tupu

This will:
1.Create a new user tupu.

2.Automatically create the home directory /home/tupu.

3.Set the default shell to /bin/bash.

4.Prompt for password creation and additional user details.

 # Tupu (Using) To create the user lupu, use the following command:

            sudo useradd -m -d /home/lupu -s /bin/bash -G lupu lupu

This will:

1.Create the user lupu

2.Set the home directory to /home/lupu

3.Assign the default shell /bin/bash

4.Add lupu to the lupu group            

# Set a password for lupu:

            sudo passwd lupu


Hupu (System User) To create a system user hupu with restricted login, use:            

            sudo useradd --system --shell /bin/false hupu

Granting Sudo Privilege Method 1: Using (Recommended) Edit the sudoers file safely:  
                sudo visudo  

Method 2: Adding Users to the Group Alternatively, run:

                sudo usermod -aG sudo tupu
                sudo usermod -aG sudo lupu

Verify with:

            groups tupu
            groups lupu

3.Setting Up Shared directory Step 1: Create the directory

         sudo mkdir /opt/projekti

Step 2: Create and Assign a Group

            sudo groupadd projekti
            sudo usermod -aG projekti tupu
            sudo usermod -aG projekti lupu

Step 3: Set Directory Ownership

            sudo chown :projekti /opt/projekti

Step 4: Set Permissions

            sudo chmod 770 /opt/projekti

Step 5: Ensure New Files Inherit Group Ownership

            sudo chmod g+s /opt/projekti

This ensures that new files in /opt/projekti inherit the projekti group

4.Verification Check user groups:

             groups tupu
             groups lupu

Check directory permissions

            ls -ld /opt/projekti




# Output
    drwxrws--- 2 root projekti 4096 Jan 30 18:37 /opt/projekti


# Summary i get learn by doing this exercise




# output result:

![alt text](<lotus linux assisgnment 3.png>)


