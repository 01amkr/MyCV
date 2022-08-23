[//]: <> (Question 1)
# Patient Management Website
Website made using LAMP Stack

## Installation
Step 1: Open Linux terminal and Install
apache, mysql servers and php using following commands:

```bash
sudo apt update
sudo apt install apache2
sudo apt install mysql-server
sudo apt install php libapache2-mod-php
```
Adjust firewall settings:
```bash
sudo ufw app list
sudo ufw allow in "Apache"
sudo ufw status
```
Check Apache2 Ubuntu Default Page:
http://your_server_ip

Step 2: Set up mysql root user with password using:
```bash
sudo mysql_secure_installation
```


Step 3:Create the directory for your_domain as follows:
sudo mkdir /var/www/aman_kumar

Step 4: Next, assign ownership of the directory with the $USER environment variable, which will reference your current system user:
```bash
sudo chown -R $USER:$USER /var/www/aman_kumar
```

Step 5: Inside the folder /var/www/aman_kumar make a project folder.
Inside the folder make files index.php  ,update.php ,add.php,delete.php,connect.php and style.css

Set Virtual Host by this code and paste this config in blank page:
```bash
sudo nano /etc/apache2/sites-available/your_domain.conf
```
<VirtualHost *:80>
    ServerName your_domain
    ServerAlias www.your_domain
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/your_domain
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

Enable virtual Host:
```bash
sudo a2ensite your_domain
sudo a2dissite 000-default
sudo apache2ctl configtest
sudo systemctl reload apache2
```

## Setting files and Database
### Database Setup
Create mysql user and grant privileges to the user
```bash
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'user'@'localhost';
FLUSH PRIVILEGES;
```
Login to the mysql user made:
```bash
mysql -u user -p
```
Create database and table:
```bash
CREATE DATABASE patientdb;
USE patientdb;
mysql> CREATE TABLE patientdb.patienttb(
    -> Id INT AUTO_INCREMENT,
    -> Patient_name VARCHAR(255),
    -> Fees_Paid VARCHAR(255),
    -> Patient_section VARCHAR(255),
    -> Date VARCHAR(255),
    -> PRIMARY KEY(Id)
    -> );
```

WEBSITE Description:
Patient Management website with CRUD operations .

### PHP File Description
PHP and HTML code written in index.php & all others made in assign folder in /var/www/aman_kumar.
The website contains a static plain html part where add,update ,delete,view are written where PHP is used to connect to the database and send the submitted  details to insert into the mysql database.

Create connection to database using: \
$con = new mysqli($server, $username, $password, $database);

Execute the query: \
$con->query($sql)



## Deployment
To run this website go to web browser and open the following link
```bash
  localhost/project/index.php
```
## Tech Stack
**Front-end:** HTML5, CSS3 \
**Back-end:** Php \
**Database:** Mysql

## Author
- BT20CSE009 (AMAN KUMAR)
