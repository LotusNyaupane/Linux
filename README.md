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


# Assisgnment 6 APT
Check your system APT version:
 While cheaking my system version  using apt --version i get the following output
 $ apt --version

#  Output
apt 2.7.14 (amd64)
![alt text](<Lotus APT-1.png>)

Update the package list:

  command:
           
           sudo apt update
  
Why this step is important?
 From this command  we can update the package list from the repositories.
 aditionally ,It fetches information about the latest available versions of packages.

3.Upgrade installed packages:

Code:

     sudo apt upgrade -y

![alt text](<lotus new apt.png>) 

What is the difference between update and upgrade?
The diffrence between the update and upgrade is:

•  apt update = this command refreshes the list of available packages.

•  apt upgrade =  this command  help to Install new versions of the installed packages.


4.View pending updates (if any):

command:

       apt list --upgradable

Output:

     Listing ...Done


2. Installing & Managing Packages:

     5.Search for a package using APT:

     code:

        apt search image editor



In this package i had used Gimp 
![alt text](<lotus gimp package.png>)


6.View package details:

![alt text](<gimp inf1.png>) ![alt text](<gimp inf22.png>)


So the dependencies it require is 

```
Depends: libgimp2.0t64 (>= 2.10.36),  libgdk-pixbuf-2.0-0 (>= 2.30.8), libgegl-0.4-0t64 (>= 1:0.4.38), libgexiv2-2 (>= 0.10.6), libglib2.0-0t64 (>= 2.79.0), libgs10 (>= 9.10~dfsg), libgtk2.0-0t64 (>= 2.24.10), libgudev-1.0-0 (>= 167), libharfbuzz0b (>= 0.6.0), libheif1 (>= 1.13.0), libjpeg8 (>= 8c), libjson-glib-1.0-0 (>= 1.5.2), libjxl0.7 (>= 0.7.0), liblcms2-2 (>= 2.9), liblzma5 (>= 5.1.1alpha+20120614), libmng2 (>= 2.0.2), libmypaint-1.5-1 (>= 1.5.0), libopenexr-3-1-30 (>= 3.1.5), libopenjp2-7 (>= 2.0.0), libpango-1.0-0 (>= 1.29.4), libpangocairo-1.0-0 (>= 1.29.4), libpangoft2-1.0-0 (>= 1.29.4), libpng16-16t64 (>= 1.6.2), libpoppler-glib8t64 (>= 0.44.0), librsvg2-2 (>= 2.32.0), libstdc++6 (>= 13.1), libtiff6 (>= 4.0.3), libwebp7 (>= 1.3.2), libwebpdemux2 (>= 1.3.2), libwebpmux3 (>= 1.3.2), libwmf-0.2-7 (>= 0.2.12), libwmflite-0.2-7 (>= 0.2.12), libx11-6
```

### 7.Install the package:

code:

     sudo apt install gimp -y

### Confirmation:
```
 The package was sucessfully installes without any errors
```
### 8. Check installed package version:
- **this command shows the installed version of the package.**
- **run**

### command:
```
apt list --installed | grep gimp
```
### output:
```
gimp/noble-updates,now 2.10.36-3ubuntu0.24.04.1 amd64 [installed]
```
# Part 3: Removing & Cleaning Packages (10 min)
### 9. Uninstall the package

### command:

```
sudo apt remove gimp -y
```

### output:
![alt text](<lotus remove.png>)


### 10.Remove configuration files as well:

### code:
```
 sudo apt purge gimp -y
 ```
### difference between remove and purge

- **remove- uninstalls the package but leaves configuration files.**
- **removes the package along with its configuration files.**

## 11.Clear unnecessary package dependencies:
```
sudo apt autoremove -y
```
### output:
**This command removes unused dependencies that were installed with GIMP but are no longer needed by any package.**

## 12.Clean up downloaded package files:
```
sudo apt clean
```
### Part 4:Managing Repositories & Troubleshooting (15 min)

## 13.List all the repositories:
- **I had noticed that ,in this files lists the software sources that which are using API to download diffrent package it includes the URls for updating and installing packages.**
- **Run**

### Command:
```
cat /etc/apt/sources.list
```
## 14.Add a new repository (example: universe repository):
- **Run**
### command:

- **The package which are found in this universal repository are community-maintained open-sources packages.**
## 15. Simulate an installation failure and troubleshoot:

## command:
```
sudo apt install fakepackage
```
## Eroor message:
```
unable to locate the fakepackage
```
## the things that i followed to troubleshoot the issue:
- **Make insure the name of the package given is correct**
- **recheak the repositories containing the package is enabled.**
- **update the package list with ``` sudo apt update ``` to be sure that the current package information.**

### Run:
```
sudo apt update

```

# Bonus challange(optional):
- **use  ```apt-mark``` to hold and unhold a package**
### Run:
```
sudo apt-mark hold gimp
sudo apt-mark unhold gimp
```
- **holding a package saves it from being atomatically updates which is extremely important for making sure of stability or compativility while using other diffrent software.**
![alt text](<lotus last.png>)

# Assisgnment 8- Firewall 

1. Introducing this report details the firewall setup for protecting a server by permetting essential services and also preventing the unauthorized acess and also reducing the typical network threats .The Firewall regulations aare intented to 

- Allow essestial services(OpenSSH,HTTP and HTTPS)
- Log blocked and allowed connections for monotoring



### Install iptables and iptables-persistent
```
sudo apt update
sudo apt install iptables iptables-persistent
```
Purpose: To Install the necessary tools (iptables for firewall configuration and iptables-persistent to save rules across reboots).

#### Step 2: Define Default Firewall Policies 

```
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT
```

* Why Defined:
 INPUT DROP: Blocks all incoming traffic by default. Only explicitly allowed traffic will be accepted.

FORWARD DROP: Blocks all forwarded traffic (useful if the server is not acting as a router).

OUTPUT ACCEPT: Allows all outgoing traffic from the server.

 * Purpose:
Ensures the server is secure by default, blocking all unauthorized traffic.

### Step 3: Allow Loopback Traffic
```
iptables -A INPUT -i lo -j ACCEPT
iptables -A OUTPUT -o lo -j ACCEPT
```
### Step 4: Allow Established and Related Connections

```
iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
```
- As it Allows traffic for already established connections and related traffic.

- purpose: Ensures that legitimate traffic is not blocked while maintaining security.


### Step 5: Allow OpenSSH (Port 22)
```
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```
#### Step 6: Allow HTTP (Port 80) and HTTPS (Port 443)
```
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```
### Step 7: Log Blocked Traffic
```
iptables -A INPUT -j LOG --log-prefix "Blocked Traffic: "
```
- Why Defined:
Logs all incoming traffic that is blocked by the firewall.

- Purpose:
Helps in monitoring and troubleshooting blocked traffic.

### Step 8: Log Allowed Traffic
```
iptables -A INPUT -j LOG --log-prefix "Allowed Traffic: "
```

- Why Defined:
Logs all incoming traffic that is allowed by the firewall.

- Purpose:
Provides visibility into legitimate traffic for auditing and analysis.

#### Step 9: Mitigate SYN Flood Attacks
```
iptables -A INPUT -p tcp --syn -m limit --limit 1/s --limit-burst 3 -j ACCEPT
iptables -A INPUT -p tcp --syn -j DROP
```
- Why Defined:
Limits the rate of SYN packets (used to initiate TCP connections) to 1 per second, with a burst limit of 3.

Drops any additional SYN packets beyond this limit.

- Purpose:
Protects the server from SYN flood attacks, which can overwhelm the server with connection requests.

#### Step 10: Prevent ICMP Flood (Ping Flood)
```
iptables -A INPUT -p icmp --icmp-type echo-request -m limit --limit 1/s -j ACCEPT
iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
```
- Why Defined:
Limits the rate of ICMP echo requests (ping requests) to 1 per second.

Drops any additional ping requests beyond this limit.

- Purpose:
Protects the server from ICMP flood attacks, which can overwhelm the server with ping requests.

#### Step 11: Save Rules and Make Them Persistent
```
iptables-save > /etc/iptables/rules.v4
```
- Why Defined:
Saves the current iptables rules to a file (/etc/iptables/rules.v4).

- Purpose:
Ensures that the firewall rules are loaded automatically at startup
#### Step 12: Verify the Rules

```
sudo iptables -L -v -n
```
- Why Defined:
Lists all iptables rules with packet/byte counts.

- Purpose:
Verifies that the rules have been applied correctly.

#### Step 13: Monitor Logs
```
sudo tail -f /var/log/syslog | grep -E "Blocked Traffic: | Allowed Traffic: "
```
- Why Defined:
Monitors logs for blocked and allowed traffic.

- Purpose:
Ensures that the logging rules are working as intended.

#### Step 14: Test the Configuration
```
ping 192.168.1.100
```
Resutls:
![alt text](<Screenshot 2025-03-05 221412.png>) ![alt text](<Screenshot 2025-03-05 221419.png>)










   
























