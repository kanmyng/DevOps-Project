# Linux Fundamentals
## Overview
This guide provides a comprehensive approach to understanding, installing, and managing Linux servers on AWS and virtual environments, 
ensuring a robust foundation for cloud computing skills.
## Linux
Linux is a free, open-source operating system known for its stability, security, and flexibility. Unlike Windows or macOS, it's widely used for servers and supercomputers. Users can modify and distribute their versions. Linux runs on various devices, from desktops to smartphones, and powers much of the internet's infrastructure. A global community of developers supports its numerous distributions, tailored to different needs.

## Understanding Linux Distributions
Linux comes in various distributions (distros), each tailored to different use cases and user preferences. Here's a closer look at some popular distributions:
### Ubuntu
        • Overview: Ubuntu is one of the most user-friendly Linux distributions, making it a popular choice for beginners.
        • Features: It offers a vast repository of software, a strong focus on usability, and regular updates.
        • Use Cases: Ideal for desktops, laptops, and servers, Ubuntu is often the first choice for those new to Linux.
### CentOS
        • Overview: CentOS is a free, community-supported distribution that is functionally compatible with Red Hat Enterprise Linux (RHEL).
        • Features: Known for its stability and reliability, CentOS is preferred for enterprise environments.
        • Use Cases: Commonly used for servers and enterprise-grade applications, it provides a robust platform for hosting and development.
### Fedora
        • Overview: Fedora is a cutting-edge distribution that focuses on integrating the latest technologies.
        • Features: It offers a sleek user interface and is often used as a testing ground for new features before they are included in Red Hat Enterprise Linux.
        • Use Cases: Ideal for developers and users who want to experiment with the latest software and technologies.
### Red Hat Enterprise Linux (RHEL)
        • Overview: RHEL is a commercial distribution company that offers enterprise-level support and services.
        • Features: It provides a secure, stable, high-performance platform with long-term support.
        • Use Cases: Widely used in enterprise environments, RHEL is the go-to choice for mission-critical applications and large-scale deployments.
## Hands-On
### Practical Guide to Installation and Initial Setup of Linux Servers on AWS
AWS (Amazon Web Services) provides powerful tools for deploying and managing virtual servers through EC2 (Elastic Compute Cloud). This guide offers a concise, hands-on introduction to setting up and managing a Linux server on AWS. Here is how to provision, configure, and securely connect to the server, equipping you with essential cloud computing skills.
### Linux Installation and Setup: Creating a Linux Server on AWS EC2
#### 1. Sign up and sign in to your AWS account.
        • Visit the [AWS website](https://aws.amazon.com/) and create an account if you don't already have 
![AWS Sign-up Page](./img/1.AWS.png)
        • Follow the prompts to complete the registration process and verify your email address.
![AWS Registration](./img/2.AWS.png)
        • Sign in to the AWS Management Console using your credentials.
![AWS Sing-in](./img/3.AWS.png)
#### 2. Provisioning an Ubuntu server on AWS
##### i. Navigate to the EC2 Dashboard by selecting "EC2" under the "Compute" category.
        • Click on "Services" at the top of the page.
        • Scroll down to the "Compute" category.
        • Click on "EC2.
![ECS](./img/4.NAWS.png)
##### ii. Click on "Launch Instance" to start the process of creating a new EC2 instance.
![Launch EC1](./img/5.AWS.png)
##### iii.	Choose an Amazon Machine Image (AMI). For this setup, select an Ubuntu Server AMI (e.g., Ubuntu Server 20.04 LTS).
##### iv.	Select an instance type based on your needs (e.g., t2.micro for the free tier).
##### v.	Configure the instance details, storage, tags, and security group settings as needed.
##### vi.	Review and launch the instance. When prompted, create or select an existing key pair and download the .pem file.
##### vii.	After launching the instance, note the instance ID, public IP address, or public DNS.
##### viii.	Ensure your security group allows SSH access (port 22) from your IP address
#### 3. Connecting to the server 
##### I. A client tools 
        • Client tools enable users to communicate with and render commands to the server, either locally or remotely.
        • Examples include PuTTY, GitBash, PowerShell, MobaXterm, and Command Prompt on Windows, or Terminal on macOS.
##### ii. A secure protocol 
        • A secure protocol ensures that the information relayed to the remote server is protected from unauthorized access.
        • The Secure Shell (SSH) protocol is commonly used for secure remote connections.
##### iii. Example of client tools 
        • PuTTY: A free and open-source terminal emulator, serial console, and network file transfer application.
        • GitBash: A package that provides Git command-line features and a Bash emulator on Windows.
        • PowerShell: A task automation framework from Microsoft, consisting of a command-line shell and associated scripting language.
        • MobaXterm: An enhanced terminal for Windows with an X11 server, tabbed SSH client, and other network tools.
        • Command Prompt (cmd): A command-line interpreter application available in most Windows operating systems.
        • Terminal: The terminal emulator included in macOS, used to access the command line interface.         
#### 4. Connecting to EC2 instance on AWS 
#####  I. Launch an EC2 instance
        • Ensure you have an EC2 instance running. Note the instance ID, public IP address, or public DNS.
![EC2 Instance](./img/6.AWS.png)
##### ii. Locate the key pair file
        • When you created the instance, you selected or created a key pair (a .pem file). Ensure you have access to this file, as it is needed to connect to the instance.
##### iii. Set and locate the appropriate directory of the key pair file
        • Open a terminal on your local machine and navigate to the directory containing your key pair file.
##### iv. Connect to the EC2 instance
        • Use the SSH command to connect to your instance. The command will look like this.
![EC2 Instance](./img/7.AWS.png)

Use the ssh command to connect to your instance. The command will look like this and can be found on the EC2 instance as shown in the screenshot below.
![SSH Commane](./img/8.AWS.png)
##### v. Set and locate the appropriate directory of the key pair file
        • Open a terminal on your local machine and navigate to the directory containing your key pair file.
![locate folder](./img/9.AWS.png)
##### vi. Connect to the EC2 instance
        • Use the ssh command to connect to your instance. The command will look like this:
![EC2 Command](./img/10.AWS.png)
##### vii. Accept the connection
        • The first time you connect, you may see a message asking if you want to continue connecting. Type yes and press Enter.
![EC2 Yes](./img/11.AWS.png)
You are connected
        • If everything is set up correctly, you should now be logged into your EC2 instance. The command prompt will change to indicate you are on the remote server.
![EC2 Connect](./img/12.AWS.png)
##### viii. To connect to an EC2 instance remotely using the key pair file path
![.perm path](./img/13.AWS.png)

This command tells SSH to use the specified key pair file for authentication and to connect to the EC2 instance at the given IP address using the specified username.
![Connect via path](./img/14.AWS.png)
Accept the connection: The first time you connect, you may see a message asking if you want to continue connecting. Type yes and press Enter
![Connect](./img/15.AWS.png)

##### You are connected: 
You should be logged into your EC2 instance if everything is set up correctly. The command prompt will change to indicate you are on the remote server. 
![Connect](./img/16.AWS.png)
##### Here's a detailed explanation of each part of this command:
    • ssh -i: This starts the SSH command and specifies that you're using an identity file (key pair) for authentication.
    • C:\Users\kanmy\Downloads\EC2_Mini.pem: This is the full path to your key pair file on your local machine.
    • C:\Users\kanmy\Downloads\: This part indicates the directory where your key pair file is located.
    • EC2_Mini.pem: This is the name of your key pair file.
    • ubuntu@3.135.240.50: This specifies the remote user and the public IP address of your EC2 instance.
    • ubuntu: This is your username to connect to the instance. For Ubuntu instances, the default username is Ubuntu.
    • 172.31.21.57: This is the public IP address of your EC2 instance

### Hands-On Experience with Virtual Machines
To gain practical experience, I installed various Linux distributions on virtual machines using Oracle VirtualBox and VMware. This approach provided valuable insights into the installation process and the nuances of running Linux in a virtualized environment.
#### Installing Linux on Oracle VirtualBox
#### 1. Download and Install VirtualBox:
        • Visit the [Oracle VirtualBox website](https://www.virtualbox.org/wiki/Downloads) and download the installer for your operating system.
        • Follow the installation prompts to set up VirtualBox on your machine.
![Oracle VirtualBox](./img/1.VM.png)
#### 2.	Download Linux ISO:
        • Choose the Linux distribution you want to install (e.g., Ubuntu, CentOS) and download the ISO file from the official website.
![Ubuntu ISO](./img/UB.png)
#### 3.	Create a New Virtual Machine:
        • Open VirtualBox and click on "New" to create a new virtual machine.
![Create New VM](./img/VIRT.png)
        • Enter the name, type, and version of the operating system.
![Name VM](./img/0.VM.png)
        • Allocate memory and create a virtual hard disk for the VM.
![Hardware](./img/4.VIRT.png)
![Disk](./img/5.VIRT.png)
![Summary](./img/01.VM.png)
#### 4.	Install Linux:
        • Start the virtual machine and select the downloaded ISO file as the startup disk.
![Launch VM](./img/02.VM.png)   
        • Follow the on-screen instructions to complete the Linux installation.
![Complete VM](./img/03.VM.png)  
### Installing Linux on VMware
#### 1.	Download and Install VMware:
        • Visit the [VMware website](https://www.vmware.com/info/workstation-player/evaluation)and download VMware Workstation or VMware Player.
![Download VM](.img/1.WVM.png)
        • Install the software by following the provided instructions.
![VMWare Workstation](./img/2.WVM.png)
#### 2.	Download Linux ISO:	
        • Visit [Ubuntu website](https://ubuntu.com/download/desktop) Download the ISO file.
![Ubuntu ISO](./img/UB.png)
#### 3.	Create a New Virtual Machine:
        • Open VMware and select "Create a New Virtual Machine."
![Create New VM](./img/3.WVM.png)
        • Follow the setup wizard, specifying the ISO file and configuring the VM settings.
![Load ISO Image](./img/4WVM.png)
![Load ISO Image](./img/4.WVM.png)
![Load ISO Image](./img/5.wvm.png)


        
#### 4.	Install Linux:
        • Power on the virtual machine and proceed with the Linux installation by following the guided prompts.

### Troubleshooting Guide
When working with Linux servers on AWS or virtual machines, encountering various issues is common. This troubleshooting guide offers solutions for frequently faced problems.
#### ON AWS EC2 Instances
##### 1. Instance Not Launching
        I. Cause: Insufficient permissions or quota limits.
        II. Solution: Check permissions and EC2 service limits.
##### 2. Cannot Connect to Instance
        I. Cause: Incorrect security group settings.
        II. Solution: Allow inbound traffic on port 22 (SSH) and whitelist your IP address.
##### 3. Permission Denied (Public Key)
        I. Cause: Incorrect key pair file permissions.
        II. Solution: Use chmod 400 your-key-pair.pem to set correct permissions.
##### 4. Instance Stuck in Stopping/Terminating
        I. Cause: AWS issues or hardware problems.
        II. Solution: Contact AWS support or force-stop via AWS Management Console or CLI.
##### 5. Slow Instance Performance
        I. Cause: Under-provisioned instance type.
        II. Solution: Upgrade to a more powerful instance type.
##### 6. Cannot Access Hosted Web Server
        I. Cause: Incorrect security group/firewall settings.
        II. Solution: Allow inbound traffic on port 80 (HTTP) or 443 (HTTPS) and verify firewall settings.

#### On Virtual Machines
##### 1. VM Won’t Start
        I. Cause: Insufficient system resources.
        II. Solution: Ensure adequate CPU, memory, and disk space. Close other applications.
##### 2. Cannot Mount ISO File
        I. Cause: Incorrect ISO file or misconfiguration.
        II. Solution: Verify ISO integrity and correct startup disk configuration.
##### 3. Network Connectivity Issues
        I. Cause: Misconfigured network settings.
        II. Solution: Check network adapter settings (NAT or Bridged mode).
##### 4. Slow VM Performance
        I. Cause: Limited resources or high host load.
        II. Solution: Allocate more RAM and CPU cores. Reduce host machine load.
##### 5. Guest Additions Not Working (VirtualBox)
        I. Cause: Improper installation.
        II. Solution: Reinstall via "Devices" > "Insert Guest Additions CD image".
##### 6. VMware Tools Not Installed
        I. Cause: Not installed or outdated.
        II. Solution: Install/update via "VM" > "Install VMware Tools".

