[//]: <> (Question 1)
# Patient Management Website
Website made using LAMP Stack

## Installation
Step 1: Open Linux terminal and Install
apache, mysql servers and php using following commands:

```bash
sudo apt install apache2
sudo apt install mysql-server
sudo apt install php libapache2-mod-php
```
Step 2: Set up mysql root user with password using:
```bash
sudo mysql_secure_installation utility
```


Step 3:Create the directory for your_domain as follows:
sudo mkdir /var/www/aman_kumar

Step 4: Next, assign ownership of the directory with the $USER environment variable, which will reference your current system user:
sudo chown -R $USER:$USER /var/www/aman_kumar

Step 5: Inside the folder /var/www/aman_kumar make a project folder.
Inside the folder make files index.php  ,update.php ,add.php,delete.php,connect.php and style.css

Step 6: Using the following commands download Mysql drivers
(which are necessary for connection).
```bash
sudo apt-add-repository ppa:ondrej/php
sudo apt-get install php7.0
apt-get install php7.4-mysql
service apache2 restart
```
Step 7: Start the apache and mysql server
```bash
sudo service apache2 start
sudo service mysql start
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
PHP and HTML code written in index.php made in assign folder in /var/www/aman_kumar.
The website contains a static plain html part where details of the authors and the assignment is given
Website also contains a html form where PHP is used to connect to the database and send the submitted form details to insert into the mysql database.

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
