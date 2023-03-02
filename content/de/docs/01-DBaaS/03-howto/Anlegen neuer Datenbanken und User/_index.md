---
title: "Anlegen neuer Datenbanken und User"
linkTitle: "Anlegen neuer Datenbanken und User"
weight: 2
date: 2023-02-21
---


Grant Access to a User from a Remote System
In this section, we will create a new database named newdb and a user named newuser, and grant access to the remote system to connect to the database newdb as user newuser.

First, log in to the MariaDB shell with the following command:
``$ mysql -u admin -p``

Provide your admin (root) password as shown in the Webdock backend and when you get the prompt create a database and user with the following command:
``MariaDB [(none)]> CREATE DATABASE newdb;
MariaDB [(none)]> CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';``

Next, you will need to grant permissions to the remote system with IP address 62.138.222.4 to connect to the database named newdb as user newuser. You can do it with the following command:

MariaDB [(none)]> GRANT ALL ON newdb.* to 'newuser'@'62.138.222.4' IDENTIFIED BY 'password' WITH GRANT OPTION;

Next, flush the privileges and exit from the MariaDB shell with the following command:
``MariaDB [(none)]> FLUSH PRIVILEGES;
MariaDB [(none)]> EXIT;``

A brief explanation of each parameter is shown below:
* newdb: It is the name of the MariaDB database that the user wants to connect to.
* newuser: It is the name of the MariaDB database user.
* 62.138.222.4: It is the IP address of the remote system from which the user wants to connect.
* password: It is the password of the database user.

If you want to grant remote access on all databases for newuser, run the following command:
``MariaDB [(none)]> GRANT ALL ON *.* to 'newuser'@'62.138.222.4' IDENTIFIED BY 'password' WITH GRANT OPTION;``

If you want to grant access to all remote IP addresses on newdb as newuser, use % instead of IP address (208.117.84.50) as shown below:
``MariaDB [(none)]> GRANT ALL ON newdb.* to 'newuser'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;``

If you want to grant access to all IP addresses in the subnet 62.138.222.0/24 on newdb as user newuser, run the following command:
``MariaDB [(none)]> GRANT ALL ON newdb.* to 'newuser'@'62.138.222.%' IDENTIFIED BY 'password' WITH GRANT OPTION;``