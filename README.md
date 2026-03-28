<h1>Helpdesk Home Lab – Windows 11 Domain Join & Network Configuration (Windows Server 2022)</h1>

<h2>Description</h2>
This lab continues the HelpDesk Home Lab series by introducing client machine integration into an Active Directory environment using Windows 11.

<br />In this lab, the following tasks were completed:
- <b>Created and configured a Windows 11 virtual machine</b>
- <b>Installed Windows 11 Pro for domain compatibility</b>
- <b>Configured VirtualBox network settings (bridged and host-only adapters)</b>
- <b>Assigned static IP addresses for communication between machines</b>
- <b>Verified connectivity between client and domain controller</b>
- <b>Joined Windows 11 machine to Active Directory domain</b>
- <b>Authenticated using domain user accounts</b>
- <b>Tested domain login functionality</b>
- <b>Enabled Remote Desktop access between machines</b>

This project builds on previous labs where Active Directory Domain Services (AD DS) and user accounts were created.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Oracle VirtualBox (v7.2.6)</b>
- <b>Windows Server 2022 (64-bit)</b>
- <b>Windows 11 Installation Media (ISO)</b>
- <b>Command Prompt (CMD)</b>

<h2>Environments Used </h2>

- <b>Host Operating System: Windows 10 / Windows 11</b>
- <b>Virtualization Platform: Oracle VirtualBox</b>
- <b>Guest Operating System: Windows Server 2022</b>

<h2>Program walk-through:</h2>

<p align="center">
Step 1 – Download and Install Oracle VirtualBox<br/><br/>
Navigate to the Oracle VirtualBox website and download the latest version of VirtualBox (v7.2.6). Run the installer and follow the installation wizard to install VirtualBox on your host machine: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%201.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 2 – Download Windows Server 2022 ISO<br/><br/>
Go to the Microsoft Evaluation Center and download the Windows Server 2022 ISO (64-bit). Save the ISO file to your system so it can be used to install the server operating system inside the virtual machine: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%20II.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 3 – Download Windows 11 Installation Media<br/><br/>
Navigate to the Microsoft Windows 11 download page and download the Windows 11 Installation Media Creation Tool. Use the tool to create a Windows 11 ISO file which will later be used as a client machine in the lab environment: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%203.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 4 – Create a New Virtual Machine<br/><br/>
Open Oracle VirtualBox and click “New” to create a new virtual machine. Name the virtual machine Server 2022 and select Microsoft Windows as the operating system type with Windows Server 2022 as the version: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%204.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 5 – Allocate System Resources<br/><br/>
Configure the hardware settings for the virtual machine. Assign 8GB of RAM and 2 CPU cores to the virtual machine to ensure the server runs smoothly during installation and future lab exercises: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%205.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 6 – Mount the Windows Server 2022 ISO<br/><br/>
Open the virtual machine settings and navigate to the Storage section. Attach the downloaded Windows Server 2022 ISO file to the virtual optical drive so the virtual machine can boot from it during installation: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%206.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 7 – Start the Virtual Machine<br/><br/>
Start the virtual machine in VirtualBox. When prompted, select the Windows Server 2022 ISO file and allow the system to boot into the Windows Server installation setup: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%207.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 8 – Install Windows Server 2022<br/><br/>
Follow the Windows installation prompts and select Windows Server 2022 (Desktop Experience) to install the version with the graphical user interface. Choose Custom Installation and proceed using the default disk configuration: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%208.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 9 – Configure the Administrator Account<br/><br/>
After installation completes, the system will prompt you to set a password for the Administrator account. Enter a secure password and press Ctrl + Alt + Delete to log into the server for the first time: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%209.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 10 – Remove the Installation ISO<br/><br/>
Once the installation finishes and the server boots successfully, remove the Windows Server 2022 ISO from the virtual machine’s storage settings to prevent the VM from booting into the installer again: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%2010.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 11 – Adjust Time Zone Settings<br/><br/>
Open the system settings and configure the correct time zone for the server environment to ensure system time and logs are accurate: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%2011.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 12 – Test Shutdown and Restart Commands<br/><br/>
Opened Command Prompt and tested the system management command shutdown /i looked at other shutdown options using shutdown /?. These commands demonstrate different ways to shut down or restart the server using both the GUI and command line: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-Server-2022-Installation-Virtual-Environment-Setup/blob/main/Step%2012.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
