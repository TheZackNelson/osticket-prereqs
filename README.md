<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Prerequisites and Installation</h1>

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
You'll deploy a Windows 10 VM in Microsoft Azure, install all necessary dependencies, and fully configure osTicket for use as a web-based ticketing system.

---

<h2>🎥 Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com) *(Coming Soon)*

---

<h2>🧰 Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- MySQL Database 5.5
- PHP 7.3.8
- osTicket v1.15.8
- HeidiSQL
- PHP Manager for IIS
- Rewrite Module for IIS

---

<h2>🖥️ Operating System Used</h2>

- Windows 10 Pro (21H2)

---

<h2>📋 Lab Details</h2>

- **VM Name:** `osticket-vm`  
- **vCPUs:** 4  
- **Username:** `labuser`  
- **Password:** `osTicketPassword1!`  

---

<h2>⚙️ Installation Steps</h2>

### 🚀 VM Setup

1. Create a Windows 10 VM in Azure named `osticket-vm` with 4 vCPUs.
2. Log into the VM using Remote Desktop as `labuser`.

---

### 📂 File Preparation

3. Download and unzip the `osTicket-Installation-Files.zip` onto your Desktop.
4. Confirm you now have a folder named `osTicket-Installation-Files`.

---

### 🌐 IIS + PHP Setup

5. Install IIS with CGI:
   - Go to Control Panel → Programs → Turn Windows Features On or Off
   - Enable:  
     - `Internet Information Services`  
     - `World Wide Web Services > Application Development Features > CGI`

6. From the `osTicket-Installation-Files` folder, install:
   - `PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)`
   - `Rewrite Module (rewrite_amd64_en-US.msi)`

---

### 🧱 PHP & MySQL Setup

7. Create the folder: `C:\PHP`

8. Unzip `php-7.3.8-nts-Win32-VC15-x86.zip` into `C:\PHP`

9. Install:
   - `VC_redist.x86.exe`
   - `MySQL 5.5.62 (mysql-5.5.62-win32.msi)`  
     - Choose *Typical Setup*
     - Launch the Configuration Wizard  
     - Use *Standard Configuration*  
     - Username: `root`  
     - Password: `root`

---

### 🧩 Register PHP with IIS

10. Open IIS Manager **as Administrator**

11. Click on `PHP Manager`  
    - Register PHP: `C:\PHP\php-cgi.exe`

12. Reload IIS (Stop/Start from IIS Manager)

---

### 🛠️ osTicket Setup

13. From the `osTicket-Installation-Files` folder:
    - Unzip `osTicket-v1.15.8.zip`
    - Copy the `upload` folder to: `C:\inetpub\wwwroot`
    - Rename the folder from `upload` → `osTicket`

14. In IIS:
    - Go to `Sites > Default Web Site > osTicket`
    - On the right-hand side, click **Browse *:80**

---

### ✅ PHP Extensions

15. In IIS → Sites → Default Web Site → osTicket:
    - Open `PHP Manager`
    - Click “Enable or disable an extension”
    - Enable:
      - `php_imap.dll`
      - `php_intl.dll`
      - `php_opcache.dll`

16. Refresh your osTicket browser tab. Verify no more missing PHP extensions.

---

### 🔒 Configuration Files

17. Rename config file:
    - From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
    - To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`

18. Set permissions on `ost-config.php`:
    - Right-click > Properties > Security tab  
    - Click **Advanced** → Disable inheritance → Remove all  
    - Add new permission:  
      - Principal: `Everyone`  
      - Full Control: ✅

---

### 🗃️ Database Setup

19. Install HeidiSQL from the `osTicket-Installation-Files` folder.

20. Open HeidiSQL:
    - Create new session:
      - Username: `root`
      - Password: `root`
    - Connect to session
    - Create a new database named `osTicket`

---

### 🎉 Final Web Installer Setup

21. In the browser, continue setting up osTicket:
    - Helpdesk Name: *(your choice)*
    - Default Email: *(for receiving tickets)*
    - Database Name: `osTicket`
    - MySQL Username: `root`
    - MySQL Password: `root`
    - Click **Install Now**

22. Once installed successfully:
    - Access your helpdesk admin panel: `http://localhost/osTicket/scp/login.php`
    - End-user portal: `http://localhost/osTicket/`

---

<h2>✅ Post-Installation Notes</h2>

- Delete or restrict access to `/setup` directory
- Configure email piping or SMTP for ticket notifications
- Set up regular MySQL backups
- Keep PHP and MySQL updated
- Begin configuring Departments, Agents, and Help Topics!

---

<h2>📬 Questions or Issues?</h2>

If you're following along and need help, feel free to open an issue in this repo or comment on the walkthrough video.

---
