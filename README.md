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
<img src="https://i.imgur.com/lI98Zzq.jpg" height="80%" width="80%" alt="Internet Information Services"/>
</p>
<br />

<!--- Step 4 -->
<p>
To make sure everything is working, open up a new window and type: "127.0.0.1". You should see this page:
</p>
<p>
<img src="https://i.imgur.com/E9SOEiR.jpg" height="80%" width="80%" alt="IIS homepage"/>
</p>
<br />

<!--- Step 5 -->
<p>
Next we're going to install some software, use this link to access all the installation files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
</p>
 <h3> Do these in order: </h3>
 
  - Download PHP Manager for IIS
  - Download Rewrite Module
  - Create a directory C:\PHP
  - Download PHP 7.3.8 and extract files into the PHP folder
  - Download Microsoft Visual C++ Redistributable
  - Download MySQL Server
    - Typical 
    - Standard Configuration
    - Password: Password1
 
<br />

<!--- Step 6 -->
<p>
Next, we're going to register PHP inside of Internet Information Services (IIS) Manager. First open run IIS as an administrator and the double click on PHP Manager. You'll notice that it says that "PHP is not enabled. Register a new PHP version to enable PHP via FastCGI." Click Register new PHP version and inside the PHP folder there should be a php-cgi application. Click it, press open, and then OK.
</p>
<p>
<img src="https://i.imgur.com/G5ijybN.png" height="80%" width="80%" alt="PHP register"/>
</p>
<br />

<!--- Step 7 -->
<p>
Next, we're going to download osTicket from the installation files provided above. Once downloaded, open up the zip folder and copy the upload folder. Paste the upload folder inside C:\inetpub\wwwroot and then rename the upload folder to osTicket.
</p>
<p>
<img src="https://i.imgur.com/LrM2UEb.png" height="80%" width="80%" alt="osTicket"/>
</p>
<br />

<!--- Step 8 -->
<p>
Next, go back into Internet Information Services (IIS) Manager and click restart. On the left side of the panel, under "VM-osTicket", click the dropdown for Sites -> Default Web Site -> then click on osTicket. On the right side of the panel, click on "Browse *:80 (http)".
</p>
<p>
<img src="https://i.imgur.com/RZtH5Qt.png" height="80%" width="80%" alt="IIS"/>
</p>
<br />

<!--- Step 9 -->
<p>
Next, we're going to go back into IIS to enable some extensions for osTicket. Go into IIS -> PHP Manager -> Enable or disable an extension.
</p>

- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
<br />

<!--- Step 10 -->
<p>
Next, we're going to go to C:\inetpub\wwwroot\osTicket\include and rename the file ost-sampleconfig.php to ost-config.php.
</p>
<br />

<!--- Step 11 -->
<p>
Now we need to assign permissions for the ost-config.php file. So right click the file -> Properties -> Security -> Advanced -> Disable Inheritance -> Remove all permissions -> Add -> Select a prinicipal -> Type "Everyone" -> Check Names -> OK -> Full control -> OK -> Apply -> OK -> OK.
</p>
<br />

<!--- Step 12 -->
<p>
Next, we're going to fill in information on the osTicket Installer in the browser. Make sure to remember the information you use when filling out the form. After filling out the System Settings and Admin User, download HeidiSQL from the installation files in the link provided above. Create a database in Heidi called osTicket, and then enter these credentials for the Database Settings:
</p>

- Username: root
- Password: Password1

<p>
<img src="https://i.imgur.com/AsZiEEL.png" height="80%" width="80%" alt="osTicket Installer"/>
</p>
<br />

<!--- Step 13 -->
<p>
Lastly for clean up we need to do a couple of things:
</p>

- Delete C:\inetpub\wwwroot\osTicket\setup
- Set Permissions of ost-config.php to "Read" only
<br />

<!--- Step 14 -->
<p>
Congratulations, hopefully is is installed with no errors!
</p>

- Browse to your help desk login page: http://localhost/osTicket/scp/login.php
- End Users osTicket URL: http://localhost/osTicket/
<br />

