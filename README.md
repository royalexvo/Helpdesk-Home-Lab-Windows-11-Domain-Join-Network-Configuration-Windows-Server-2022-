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
- <b>Windows 11 Pro</b>
- <b>Command Prompt (CMD)</b>
- <b>Active Directory Domain Services (AD DS)</b>
- <b>Remote Desktop (RDP)</b>

<h2>Environments Used </h2>

- <b>Host Operating System: Windows 10 / Windows 11</b>
- <b>Virtualization Platform: Oracle VirtualBox</b>
- <b>Guest Operating System: Windows Server 2022 (Domain Controller) and Windows 11 Pro (Client Machine)</b>

<h2>Program walk-through:</h2>

<p align="center">
Step 1 – Create Windows 11 Virtual Machine<br/><br/>
Create a new VM in VirtualBox titled "Windows 11" and install Windows 11 Pro or Enterprise (Home edition will not support domain joining): <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%201.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 2 – Configure Initial VM Settings<br/><br/>
Allocate system resources (e.g., 4GB RAM) and complete Windows 11 setup. I came across a bug where Windows 11 wouldn't install unless I dedicated 3 processors: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%202.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 3 – Enable Network Connectivity<br/><br/>
Configured network adapter settings on both Windows 2022 server and the newly created Windows 11 VM. Using Host-Only Adapter for internal lab communication: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%203.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 4 – Rename the Client Machine<br/><br/>
Rename the Windows 11 system (e.g., Desktop01) and restart to apply changes: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%204.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 5 – Configure Static IP Address<br/><br/>
Changed the IPv4 properties for both Windows 2022 server and Windows 11 VM. Windows 2022 server got IP address 10.1.10.2, Subnet mask 255.0.0.0, gateway 10.1.10.1, and DNS server 10.1.10.2/10.1.10.1. Windows 11 VM got IP address 10.1.10.3, Subnet mask 255.0.0.0, gateway 10.1.10.1, and DNS server 10.1.10.2/10.1.10.1. Ensuring they can both communicate: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%205.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br />
Step 6 – Verify Domain Controller Connectivity<br/><br/>
Opened Command Prompt on Windows 11 VM and tested connectivity using ping Myforest.com. Ensuring the client can communicate with the domain controller: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%206.png?raw=true" width="80%" alt="Lab Steps"/>
<br />
Step 7 – Confirm Domain Controller Details<br/><br/>
On the server, verify domain setup and name using whoami /fqdn and confirm Active Directory is functioning: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%207.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 8 – Join Windows 11 to Domain<br/><br/>
On the Windows 11 machine right-click This PC → Properties. Select Domain or Workgroup → Change. Enter domain name (e.g., Myforest.com). Provide domain administrator credentials. Successful join will prompt confirmation: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%208.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 9 – Verify Domain Join in Active Directory<br/><br/>
On the domain controller(Windows 2022 Server), check the Computers container to confirm the client machine appears: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%209.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 10 – Log in with Domain User<br/><br/>
Switch user and log in using a domain account on the Windows 11 VM (e.g., John Doe):DOMAIN\username. Verify successful authentication.: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%2010.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 11 – Enable Remote Desktop Access<br/><br/>
On the server: Enable Remote Desktop. Add authorized users if needed. From Windows 11, connect using the server’s IP address: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%2011.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 12 – Test Remote Connection<br/><br/>
Use Remote Desktop to log into the domain controller from the Windows 11 machine and verify connectivity: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%2012.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
<br/>
Step 13 – Lab Completion<br/><br/>
At this stage, the environment includes a Domain Controller (Windows Server 2022) and a Domain-Joined Client (Windows 11). This setup enables future labs involving Group Policy (GPO), Shared folders, User management at scale, and Microsoft Intune integration: <br/>
<img src="https://github.com/royalexvo/Helpdesk-Home-Lab-Windows-11-Domain-Join-Network-Configuration-Windows-Server-2022-/blob/main/Step%2013.png?raw=true" height="80%" width="80%" alt="Lab Steps"/>
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
