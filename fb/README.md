# Facebook Clone - Project Setup & Run Guide

## Overview

This is a Facebook-like social media platform built with **PHP, MySQL, and Bootstrap**. Follow this guide to set up and run the project on your local machine.

---

## 📋 Prerequisites

* Windows OS (or any OS with XAMPP support)
* XAMPP (Apache, PHP, MySQL)
* Web Browser (Chrome, Firefox, Edge, etc.)
* Text Editor (VS Code, Notepad++, etc.) *(optional)*

---

# 🚀 Step-by-Step Setup Guide

## Step 1: Download & Install XAMPP

1. Go to Apache Friends - XAMPP.
2. Click **Download** (choose the latest stable version for Windows).
3. Run the installer:

```text
xampp-windows-x64-X.X.X-installer.exe
```

4. Follow the installation wizard:

   * Choose installation location (default: `C:\xampp`)
   * Select components: Apache, MySQL, PHP
   * Complete the installation
5. Launch XAMPP Control Panel.

---

## Step 2: Verify Project Location

Make sure the `fb` project folder is in the XAMPP web root:

```text
C:\xampp\htdocs\fb\
```

If it's not already there, copy/move the entire `fb` folder to:

```text
C:\xampp\htdocs\
```

---

## Step 3: Start Apache and MySQL

1. Open XAMPP Control Panel.
2. Click **Start** next to:

   * Apache (should show "Running" in green)
   * MySQL (should show "Running" in green)

> ⚠️ If they fail to start, check the logs or try running XAMPP as Administrator.

---

## Step 4: Access phpMyAdmin

Open your browser and visit:

```text
http://localhost/phpmyadmin
```

You should see the phpMyAdmin dashboard.

---

## Step 5: Create the Database

1. In phpMyAdmin, click **New**.
2. Database name:

```text
facebook
```

3. Collation:

```text
utf8mb4_general_ci
```

4. Click **Create**.

---

## Step 6: Import the Database Structure & Data

1. Select the **facebook** database.
2. Click **Import**.
3. Choose:

```text
C:\xampp\htdocs\fb\DB\facebook_final.sql
```

4. Click **Import**.

### Tables Created

* userlist (users data)
* postdata (posts)
* commentdata (comments)
* abusedata (activity logs)
* Other related tables

---

## Step 7: Configure Database Connection

Open:

```text
C:\xampp\htdocs\fb\config.php
```

Verify the following configuration:

```php
<?php
session_start();

$host = 'localhost';
$user = 'root';
$pass = '';
$db   = 'facebook';
$port = 3306;

$con = mysqli_connect($host, $user, $pass, $db, $port);

if (!$con) {
    die('Database connection failed: ' . mysqli_connect_error());
}
?>
```

> Note: If MySQL root has a password, replace `$pass = '';` with your password.

---

## Step 8: Access the Application

### Main Login Page

```text
http://localhost/fb/index.php
```

The login page provides:

* Regular User Login
* Admin Panel Login

---

# 🔐 Login Credentials

## Admin Login

| Field         | Value      |
| ------------- | ---------- |
| Mobile Number | 8412003013 |
| Password      | admin      |

### Login Steps

1. Open:

```text
http://localhost/fb/index.php
```

2. Enter:

   * Mobile Number: `8412003013`
   * Password: `admin`

3. Click **Log In**.

You will be redirected to:

```text
admindashboard.php
```

---

## Regular User Login

Users are stored in the `userlist` table.

### Create a Test User

1. Open:

```text
http://localhost/fb/register.php
```

2. Fill:

   * First Name
   * Last Name
   * Mobile Number
   * Date of Birth
   * Gender
   * Password

3. Click **Sign Up**.

4. Login using the registered credentials.

---

# 📁 Project Structure

```text
C:\xampp\htdocs\fb\
├── index.php
├── register.php
├── dashboard.php
├── admindashboard.php
├── profile.php
├── viewpost.php
├── postbackend.php
├── profile_backend.php
├── notification.php
├── logout.php
├── config.php
├── logo.png
├── DB/
│   ├── facebook_final.sql
│   ├── facebook_new.sql
│   ├── facebook.sql
│   └── facebook31-03-2023.sql
├── uploads/
└── README.md
```

---

# ✅ Admin Panel Features

### View Users

* Total registered users
* User details
* Gender, DOB, mobile number, etc.

### View Posts

* Total posts
* Post details

### View Comments

* Comment count
* Comment details

### Activity Logs

* Abuse reports
* User activity tracking

---

# 🐛 Troubleshooting

## Access Denied Error

```text
Access denied for user 'root'@'localhost'
```

### Solution

* Add MySQL password in `config.php`
* Or reset MySQL root password

---

## Connection Refused

### Solution

* Start Apache
* Start MySQL

---

## Database Tables Not Found

### Solution

Re-import:

```text
DB/facebook_final.sql
```

---

## Images Not Displaying

### Solution

Ensure `uploads` folder has write permissions.

---

# 🌐 Quick URL Reference

| Page            | URL                                    |
| --------------- | -------------------------------------- |
| Login           | http://localhost/fb/index.php          |
| Register        | http://localhost/fb/register.php       |
| User Dashboard  | http://localhost/fb/dashboard.php      |
| Admin Dashboard | http://localhost/fb/admindashboard.php |
| Profile         | http://localhost/fb/profile.php        |
| phpMyAdmin      | http://localhost/phpmyadmin            |

---

# 💡 Tips & Best Practices

### Session Timeout

* Sessions expire after logout or browser close.
* Always logout properly.

### Database Backup

Export backups regularly using phpMyAdmin.

### Security Notes

* Do not use these credentials in production.
* Admin credentials are hard-coded.
* Use prepared statements to prevent SQL injection.

### File Uploads

* Uploaded files are stored in the `uploads` folder.
* Ensure correct folder permissions.

---

# 🆘 Need Help?

### Check Logs

**Apache Log**

```text
C:\xampp\apache\logs\error.log
```

**MySQL Log**

```text
C:\xampp\mysql\data\
```

### Verify

* Apache is running
* MySQL is running
* phpMyAdmin is accessible
* Database credentials are correct

---

# ✨ Summary

## Quick Setup Checklist

* [ ] Install XAMPP
* [ ] Start Apache & MySQL
* [ ] Create `facebook` database
* [ ] Import `facebook_final.sql`
* [ ] Verify `config.php`
* [ ] Open `http://localhost/fb/index.php`
* [ ] Login as Admin or Register a User

🎉 **Your Facebook Clone is ready to use!**

---

**Last Updated:** July 7, 2026
