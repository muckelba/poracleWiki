---
title: MySQL
nav_order: 2
layout: default
parent: v3
---

# MySQL

A MySQL or MariaDB database is required to store registered users/channels and their trackings  
  
**Please do not use your scanner database for PoracleJS! Create a new one!**

Just go ahead and create a new DB user and database:

## Creating a Database and a User

If Poracle connects to the database locally, you can give it only local access rights:
   ```sql
   CREATE DATABASE poracle;
   CREATE USER 'poracle'@'localhost' IDENTIFIED BY 'poraclePassword';
   GRANT ALL PRIVILEGES ON poracle . * TO 'poracle'@'localhost';
   exit
   ```
   
Alternatively, you can grant your user access from anywhere:
   ```sql
   CREATE DATABASE poracle;
   CREATE USER 'poracle'@'%' IDENTIFIED BY 'poraclePassword';
   GRANT ALL PRIVILEGES ON poracle . * TO 'poracle'@'%';
   exit
   ```
