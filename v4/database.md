---
title: Database
nav_order: 3
layout: default
parent: v4
---

# Database

Poracle stores a record or users and their trackings in a database.

You can choose between Sqlite (default) and MySQL/MariaDB

**Please do not use your scanner database for PoracleJS!**

## Sqlite 

Default option for storing trackings is a sqlite file. 
if your database client is not configured to something else, this would be automatically created when you first launch the bot or migrate from V3

## MySql 

Just go ahead and create a new DB user and database:

### Creating a Database and a User

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
