# GLPI Ubuntu Lab Project

Ubuntu-based GLPI Home Lab simulating a real-world IT Service Desk environment. The project demonstrates deployment of a full ticketing system integrated with a LAMP stack, Windows client access, and enterprise-style service workflow.

---

## Overview

This project demonstrates the deployment of a simulated IT support environment using the GLPI ticketing system on Ubuntu Server.

The objective was to replicate a realistic enterprise helpdesk setup, including server configuration, database integration, web application deployment, and client-side access validation.

The lab focuses on practical IT Support, System Administration, and troubleshooting skills relevant to Junior IT / Helpdesk roles.

---

## Technologies Used

- Ubuntu Server 26.04
- GLPI 11.0.7
- Apache2
- MariaDB
- PHP
- VirtualBox
- Windows Client Machine (domain user simulation)
- Active Directory (conceptual integration)

---

## Deployment Summary

### Initial System Deployment

Ubuntu Server was deployed in a VirtualBox internal network environment.

<details>
  <summary>More Information</summary>

<img width="1264" height="804" alt="image" src="https://github.com/user-attachments/assets/2c74b957-7557-46a5-9e7f-5f89f44653f1" />

- System updated using:
  `sudo apt update && sudo apt upgrade -y`
- VirtualBox Guest Additions installed:
  `sudo apt install virtualbox-guest-x11`
</details>

- IP address confirmed in internal network range (172.16.0.x)
<img width="844" height="244" alt="image" src="https://github.com/user-attachments/assets/db17daba-98ce-4d87-99ec-12770d2b9948" />

- Network connectivity validated via ICMP test to external host
<img width="512" height="69" alt="image" src="https://github.com/user-attachments/assets/292ab0a8-304d-492d-92e2-ed0bc90e8e66" />

---

### Core Services Deployment

Installed required LAMP stack components:

- Apache
```bash
sudo apt install apache2 -y
````

* MariaDB

```bash
sudo apt install mariadb-server -y
```

* PHP and required extensions

```bash
sudo apt install php php-mysql php-curl php-gd php-xml php-mbstring php-zip php-intl php-bz2 -y
```

* Apache service restart

```bash
sudo systemctl restart apache2
```

---

### SSH Access Configuration

OpenSSH server installed for remote administration:

```bash
sudo apt install openssh-server -y
```

<details>
  <summary>Service Verification</summary>

<img width="1170" height="802" alt="image" src="https://github.com/user-attachments/assets/38592286-af36-4c31-ae2b-b01d24b8c8f2" />
<img width="689" height="127" alt="image" src="https://github.com/user-attachments/assets/327a93dd-fed2-408b-b019-cc3e81602e8a" />

</details>

---

### Database Configuration

MariaDB secured and configured for GLPI:

```bash
sudo mysql_secure_installation
sudo mysql -u root -p
```

Database created:

```sql
CREATE DATABASE glpi;
```

User created:

```sql
CREATE USER 'glpiuser'@'localhost' IDENTIFIED BY 'Password1';
```

Privileges assigned:

```sql
GRANT ALL PRIVILEGES ON glpi.* TO 'glpiuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

<img width="745" height="344" alt="image" src="https://github.com/user-attachments/assets/fad33292-cb50-415b-b37b-413c7888dc57" />

---

### GLPI Installation

GLPI downloaded and deployed:

```bash
cd /var/www/
sudo wget https://github.com/glpi-project/glpi/releases/download/11.0.7/glpi-11.0.7.tgz
sudo tar -xvzf glpi-11.0.7.tgz
sudo rm glpi-11.0.7.tgz
```

Permissions configured:

```bash
sudo chown -R www-data:www-data /var/www/glpi
sudo chmod -R 755 /var/www/glpi
```

Directory structure verified: <img width="333" height="48" alt="image" src="https://github.com/user-attachments/assets/a1f70c2b-2ade-4331-b078-87e63dab9a7d" />

---

### Apache Virtual Host Configuration

GLPI virtual host configuration:

```apache
<VirtualHost *:80>
    ServerName glpi.localhost
    DocumentRoot /var/www/glpi/public

    <Directory /var/www/glpi/public>
        Require all granted

        RewriteEngine On

        RewriteCond %{HTTP:Authorization} ^(.+)$
        RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]

        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^(.*)$ index.php [QSA,L]
    </Directory>
</VirtualHost>
```

Activation:

```bash
sudo a2ensite glpi.conf
sudo a2enmod rewrite
sudo systemctl reload apache2
```

<img width="674" height="326" alt="image" src="https://github.com/user-attachments/assets/b39c1828-dcfd-48fd-b61e-55571623e7b0" />

---

### Database Verification

Verification of database availability:

```bash
sudo mysql -u root -p
SHOW DATABASES;
```

<img width="726" height="461" alt="image" src="https://github.com/user-attachments/assets/f7ba9cc6-15f4-4634-bd97-16174c0ea590" />

---

## Web-Based Installation (Client Access)

GLPI installation performed via browser from client machine:

* Access URL:

```
http://172.16.0.102
```

Initial Apache default page confirmed system routing: <img width="1910" height="955" alt="image" src="https://github.com/user-attachments/assets/f21b1df3-ab5a-4bd9-8f15-db927b6887eb" />

After disabling default site:

```bash
sudo a2dissite 000-default.conf
```

GLPI installer became accessible: <img width="1904" height="832" alt="image" src="https://github.com/user-attachments/assets/4bb9393d-650d-490c-ba78-50a1e8b55db6" />

---

### Installation Process

* Language selection
* License agreement
* System compatibility check
* Database configuration

During setup, missing PHP extensions were identified:

* bcmath
* ldap

Resolved using:

```bash
sudo apt install php-bcmath -y
sudo apt install php-ldap -y
sudo systemctl restart apache2
```

Database configuration:

* Database: glpi
* Host: localhost
* User: glpiuser

<img width="1027" height="405" alt="image" src="https://github.com/user-attachments/assets/6ed86ef2-d9b4-47fd-87fa-5eb828dfcfb2" />

Successful login after installation: <img width="1902" height="949" alt="image" src="https://github.com/user-attachments/assets/491c7d0a-9a1d-4ec2-bdf1-86af731d4a58" />

Default credentials used:

```
glpi / glpi
```

---

## Post-Installation Hardening

Security cleanup performed:

```bash
sudo rm -rf /var/www/glpi/install
sudo chmod -R 750 /var/www/glpi
```

---

## Core Features Configured

* Web-based GLPI ticketing system
* LAMP stack deployment
* Virtualized enterprise environment
* Client-server access simulation
* Basic system hardening after installation

---

## Outcome

The environment successfully simulates a functional IT Service Desk system, including server deployment, application hosting, database integration, and client-side access.

This project demonstrates practical skills in:

* Linux system administration
* Web server configuration
* Database management
* Troubleshooting and dependency resolution
* IT support workflow simulation
