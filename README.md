<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Subscription
- Azure Resource Group 
- Azure Virtual Machine

<h2>Installation Steps</h2>

<!--- Step 1 -->
<p>
To start this lab, we're going to create an Azure Resource Group named "RG-osTicket" and then create a Virtual Machine (VM) named "VM-osTicket" inside the Resource Group. During the creation of the VM, a default virtual network/subnet will be created.
</p>
<p>
<img src="https://i.imgur.com/BAOqjzr.jpg" height="80%" width="80%" alt="Virtual Machine Creation"/>
</p>
<br />

<!--- Step 2 -->
<p>
Next, we're going to use Remote Desktop Connection to connect to the Virtual Machine we created. To do this, copy the Public IP address inside the overview tab of your Virtual Machine and then paste it where it says computer and click connect. You will then be prompted to enter a username and password. Enter in the credentials you provided when you created your Virtual Machine.
</p>
<p>
<img src="https://i.imgur.com/qmXx8le.jpg" height="80%" width="80%" alt="Remote Desktop Connection"/>
</p>
<br />

<!--- Step 3 -->
<p>
Next, we're going to enable Internet Information Services (IIS) and CGI inside of the Virtual Machine. To do this go to your control panel, click on Programs, and then click on Turn Windows features on or off, and then select Internet Information Services. Next, click the dropdown next to Internet Information Services; open up World Wide Web Services; open up Application Development Features, and then select CGI.
</p>
<p>
<img src="https://i.imgur.com/lI98Zzq.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
