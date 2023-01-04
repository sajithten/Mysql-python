# How to install MySQL on Ubuntu 22.04

sudo apt update

sudo apt-get install mysql-server

systemctl is-active mysql

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123';

sudo mysql_secure_installation

sudo mysql -u root -p123

# How to install pip3

sudo apt install python3-pip

pip3 --version

# How to install mysql connector

sudo apt-get install python3-mysql.connector
or
pip3 install mysql-connector

----------------------------------------------------------------
CREATE USER 'sajith'@'localhost' IDENTIFIED BY '123';
CREATE USER 'sajith'@'%' IDENTIFIED BY '123';
GRANT ALL PRIVILEGES ON employeedb.* TO 'sajith'@'localhost';
GRANT ALL PRIVILEGES ON employeedb.* TO 'sajith'@'%';
ALTER USER 'sajith'@'localhost' IDENTIFIED WITH mysql_native_password BY '123';
ALTER USER 'sajith'@'%' IDENTIFIED WITH mysql_native_password BY '123';
FLUSH PRIVILEGES;

select Host,User,plugin from mysql.user;
-----------------------------------------------------------------

mydb = mysql.connector.connect(host='13.233.195.77',
                               database ='employeedb',
                               port='3306',
                               user='sajith',
                               password='123',
                               auth_plugin='mysql_native_password')
print("connection succesful")
mycursor = mydb.cursor()
sql = "INSERT INTO employee (empid, empname) VALUES (%s, %s)"
val = (100,"test")
mycursor.execute(sql, val)
mydb.commit()
print(mycursor.rowcount, "record inserted.")

--------------------------------------------------------------------
create database employeedb;
use employeedb;
create table employee (empid int(10),empname varchar(40));
select * from employee;
show databases;
---------------------------------------------------------------------

