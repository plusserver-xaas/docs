---
title: "Zur Datenbank verbinden"
linkTitle: "db-login"
weight: 2
date: 2023-03-16
---

## MySQL / MariaDB

Benötigte Daten finden Sie im Kundenportal

```
bburgschat@NB-63485 ~ % mysql --ssl -h node-64130e880850ca3b9a420bb9.mansvc.psmanaged.com -u kd500789 -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 42
Server version: 10.6.12-MariaDB-1:10.6.12+maria~ubu2204-log mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0,084 sec)

MariaDB [(none)]> use kd500789
Database changed
MariaDB [kd500789]> show TABLES;
Empty set (0,095 sec)

MariaDB [kd500789]> quit
Bye
bburgschat@NB-63485 ~ %
```

## PostgreSQL


