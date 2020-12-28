---
title: Installation
nav_order: 1
layout: default
parent: v3
---

# Basic installation

## Prerequisites

* [NodeJS](https://nodejs.org/en/) 8 or newer
* Dedicated [MySQL database](mysql.html) version 5.7.6 or newer


## Installation

1. Start by cloning the repository:
   ```
   git clone https://github.com/BoxService/PoracleJS.git
   ```

2. Create a [Telegram Bot](../telegrambot.html) and note your token for later.

3. Copy the config file (`cp .env.example .env`) and fill out the required options like database credentials and bottoken.

4. Install package requirements:
    ```
    npm install
    ```

5. Start Poracle:
    ```
    npm start
    ```

6. That's it, now proceed to [enter some commands](../userguide/en) or [adjust the config](config.md) further.
