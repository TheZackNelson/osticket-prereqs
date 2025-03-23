<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Prerequisites and Installation</h1>

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
You’ll learn how to set up a working osTicket environment on a Windows 10 Virtual Machine hosted on Microsoft Azure.

---

<h2>🎥 Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com) 

---

<h2>🧰 Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- MySQL Database
- PHP
- osTicket Installer

---

<h2>🖥️ Operating System Used</h2>

- Windows 10 Pro (21H2)

---

<h2>📋 List of Prerequisites</h2>

- Microsoft Azure Account
- Windows 10 Virtual Machine (VM)
- Internet Information Services (IIS) enabled
- Web Platform Installer (Web PI)
- PHP 7.3 or compatible
- MySQL Database (MySQL 5.5+ or MariaDB)
- osTicket installer files (downloaded from [osTicket.com](https://osticket.com/download))

---

<h2>⚙️ Installation Steps</h2>

<p>
<img src="https://i.imgur.com/3wBvAGv.png" height="80%" width="80%" alt="Azure VM Creation"/>
</p>
<p>
<strong>Step 1:</strong> Create a new Virtual Machine in Microsoft Azure. Select Windows 10 Pro as the operating system, choose a resource group, and configure basic settings such as region, username, and password.
</p>
<br />

<p>
<img src="https://i.imgur.com/AKCkH6E.png" height="80%" width="80%" alt="IIS Installation"/>
</p>
<p>
<strong>Step 2:</strong> Once the VM is running, connect to it using Remote Desktop. Open the Control Panel and enable Internet Information Services (IIS) with CGI and other required features for PHP support.
</p>
<br />

<p>
<img src="https://i.imgur.com/x0N2Jgf.png" height="80%" width="80%" alt="PHP and MySQL Installation"/>
</p>
<p>
<strong>Step 3:</strong> Use the Web Platform Installer to install PHP 7.3 (or newer) and MySQL Database. Be sure to set a root password for MySQL and remember it for later.
</p>
<br />

<p>
<img src="https://i.imgur.com/Y3bLZrg.png" height="80%" width="80%" alt="osTicket Files Upload"/>
</p>
<p>
<strong>Step 4:</strong> Download the osTicket installation package from the official website. Extract the files and place them in the `C:\inetpub\wwwroot` directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/fMDVN89.png" height="80%" width="80%" alt="osTicket Web Installer"/>
</p>
<p>
<strong>Step 5:</strong> Open your browser and navigate to `http://localhost/upload` (or your VM's public IP). Complete the web-based installer, entering your database credentials and creating your admin account.
</p>
<br />

<p>
<img src="https://i.imgur.com/Clzj7Xs.png" height="80%" width="80%" alt="osTicket Dashboard"/>
</p>
<p>
<strong>Step 6:</strong> Once installation is complete, remove the `/setup` directory and set permissions on the `include/ost-config.php` file to secure your environment. You should now have a fully functional osTicket help desk system!
</p>

---

<h2>✅ Post-Installation Notes</h2>

- Secure your admin panel with a strong password
- Configure email piping or SMTP for ticket notifications
- Set regular backups for your MySQL database
- Update PHP and MySQL to stay secure

---

<h2>📬 Questions or Issues?</h2>

Feel free to open an issue in this repo or reach out in the comments of the video if you're following along there!

---
