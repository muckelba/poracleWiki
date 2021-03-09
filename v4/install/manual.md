---
title: Manual Installation
nav_order: 1
layout: default
parent: Installation
grand_parent: v4
---

# Manual Installation
In this section we will discuss how to perform a manual installation. Some requirements may link to other installation guides as they will not be necessary to re-invent the wheel.

## Prerequisites
PoracleJS requires several prerequisites to operate

The following prerequisites must be installed for PoracleJS to function correctly.
 * [NodeJS](https://nodejs.org/en/)
 * [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
 * A databases is required for PoracleJS to operate properly. Only one needs to be configured for PoracleJS to operate correctly.
    * [MariaDB](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04)
    * [MySQL](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04) [MariaDB > MySQL :)]
    * [PostgreSQL](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-20-04) @TODO - Is this supported in v4?
    * [SQLite](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-sqlite-on-ubuntu-20-04)
   
### Notification Service
We will need to configure a Discord or Telegram bot to allow PoracleJS to send messages to the required service. Only one bot is required for the configuration. Both services require a token which will be used during the configuration step.

 * [Discord Bot](../../discordbot.html)
 * [Telegram Bot](../../telegrambot.html)

### Database
A database and user need to be configured for PoracleJS to access the database. While you can reuse existing users it is recommended to create a new user for each application.

#### MariaDB / MySQL
Below are examples of how to create the database and user. Please make sure to use a [strong password](https://passwordsgenerator.net/) for the user. The example password is `poraclePassword`.
If Poracle connects to the database locally, you can give it only local access rights:
   ```sql
   CREATE DATABASE poracle;
   CREATE USER 'poracleuser'@'localhost' IDENTIFIED BY 'poraclePassword';
   GRANT ALL PRIVILEGES ON poracle . * TO 'poracle'@'localhost';
   exit
   ```
   
Alternatively, you can grant your user access from anywhere:
   ```sql
   CREATE DATABASE poracle;
   CREATE USER 'poracleuser'@'%' IDENTIFIED BY 'poraclePassword';
   GRANT ALL PRIVILEGES ON poracle . * TO 'poracle'@'%';
   exit
   ```


#### PostgreSQL
@TODO

#### SQLite
If you are using SQLite there is no configuration required for PoracleJS.


## Installing PoracleJS
Now that the prerequisites have been installed we can begin installing PoracleJS. There are a few more (optional, but highly recommended) steps to help reduce any security vulnerabilities.

### Security Considerations
Before we start the installation, we should decide on a user and installation directory to use. The $HOME directory may be the simplest solution, but the *nix conventions we should use `/opt` for unbundled packages (packages not part of the OS distro). We should also not use the user `root` for the installation.

#### Creating a User
We should never install software or run programs as `root`. This is a security hole that is easy to avoid. If you already have a user you can skip this step.

For this example we will be creating a new user, pogo, that will be used for running PoracleJS. It will have its home directory in `/home/pogo`.
```bash
sudo useradd -m pogo
```

#### Creating a directory
Since we want to use `/opt` for PoracleJS we will need to create a new directory with root.
```bash
sudo mkdir /opt/PoracleJS
sudo chown pogo:pogo /opt/PoracleJS
```

### Installation
Now that we have decided on the installation directory and the user responsible for PoracleJS we can begin the installation process.

1. Ensure you are running as the correct user. If not, switch to that account with `su <username>`. An example would be `su pogo` to switch the account `pogo`.
2. Ensure you are in your installation directory. If you are using `/opt/PoracleJS` as previously indicated, you can switch here by executing `cd /opt/PoracleJS`.
3. The source of PoracleJS is hosted on GitHub. We will need to clone the repository with Git.
   ```bash
   git clone https://github.com/KartulUdus/PoracleJS.git .
   ```
4. Install PoracleJS requirements
    ```bash
    npm install
    ```
5. Clone the configuration to be used later
    ```bash
    cp config/default.json config/local.json
    ```
   
# Updating
To update the manual installation, you must perform a `git pull` in the correct directory as the installed users. If you perform a `git pull` with a user other than installed user you will run into permission errors.

An example update set of commands:
```bash
su pogo
cd /opt/PoracleJS
git pull
```

Fixing permission errors:
```bash
sudo chown -R pogo:pogo /opt/PoracleJS
```

# Auto-Starting
There are a few services that allow for easy management of a process. The easiest to use is [pm2](https://pm2.keymetrics.io/). Since we never added the user `pogo` to sudoers we will be unable to run that command. If that is the case, exit back out to root and run the command. Once installed switch back to the user created for running PoracleJS. Utilizing pm2 for auto-startup requires running the following commands:
```bash
sudo npm install pm2 -g
cd /opt/PoracleJS
pm2 start src/app.js --name poracle -u pogo
```

The following commands are useful for pm2
```bash
pm2 stop poracle # Stop PoracleJS
pm2 start poracle # Start PoracleJS
pm2 restart poracle # Restart PoracleJS
pm2 logs poracle # Show the last 15 logs for PoracleJS
pm2 monit # ASCII Dashboard for monitoring pm2
```


Congratulations! PoracleJS has been installed but we still need to configure the services to work together. Let's move onto the [configuration](./configuration) next.
