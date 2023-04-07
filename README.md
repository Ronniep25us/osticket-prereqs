# osticket-prereqs
Needed tools and prerequisites to installing osticket
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

 <a href="https://youtu.be/S9F-7JkVgAY" target="_blank_">OsTicket Install</a>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites</h2>

(Create Virtual Machine in Azure)

OSTICKET 

Your going to need to download ;
Web Platform Installer (IIS.net)
IIS 1.5.0 (IIS.net)
HeidiSQL(heidisql.com)

.Enable IIS (control panel, uninstall a program, Turn windows features on or off, select internet information services, select ok) This will create a “inetpub” folder in disk C. This creates a web server that osticket will run on.

.Download web platform installer (get from google)
.Download MySQL, PHP up to 7.3 (inside web platform installer (PHP will fail and must be manually downloaded)

.Download PHP lastest version (PHP.net)(extract folder once downloaded and copy folder to local disk, program 86x, PHP)
.
.Install PHP manager  (iis.net) download PHP manager 1.5.0 for iis 10

.Open IIS ( run as administrator)click php manager, under “PHP SETUP” click register New php version, search for the new php folder you just put in program 86x/PHP folder, open folder and select the “php-cgi.exe” then click ok.

Download OsTicket (osticket.com)extract folder, copy and paste “upload” folder to “wwwroot” folder inside the “inetpub” folder.
Rename “upload” folder to “osticket “.

Open IIS, refresh page, “osticket “ should pop up under “sites.” Click on “osticket”, then click “Browse 80(http)”, localhost/osticket/setup/ will load on webpage.

On the webpage you’ll notice all recommended extensions aren’t enabled; we will enable them with PHP manager. Open PHP manager in IIS, click “enable or disable an extension” under “PHP EXTENSIONS”, enable imap, intl, gd (if not enable) and opcache. Apcu will not be in the list. Refresh osticket page, only the last two options should be left. Click “continue.”

Last step is to create The “ost-config.php file. Go back to wwwroot folder, go to osticket, click include, go to “ost-sampleconfig”, copy and paste it in the same folder, rename the copy to“ost-config”
Right click it and click “properties” then click “security “ click “users”, click edit to change permission, click “users” again, under “Permission for Users” click “Full Control”, then click apply, then click ok. This will allow you full Access to Osticket. Go back to Osticket and click continue.

You should now see Osticket Basic Installation. Fill out the info for your help desk and admin user.

Once you get to Database settings; you must first create the database. Download “Heidisql” (heidisql.com) click “installer 32/64 bit combined “ once finished your vm may restart. Open Heidisql, click “New”. Username will remain root, enter password you’ve chose at the beginning of lab, click “open”. This will open a connection to database. Right click and “create new” and select “database” enter “Osticket “ for name.

Go back to Osticket and fill in database info.
MySQL will be “osticket “ 
Username will be “root”
Password will be the password you chose.
After you enter the info click install.

All set!! You have installed Osticket. 



