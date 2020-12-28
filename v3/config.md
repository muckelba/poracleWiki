---
title: Config File
nav_order: 3
layout: default
parent: v3
---

# Config file

Before running PoracleJS for the first time, you need to create a `.env` file. There is an example you can copy over to begin with `cp .env.example .env`.

Alternatively, you can use a json config by copying from defaults `cp config/default.json config/local.json`


## Database settings
```bash
DB_HOST=
DB_USER=
DB_PASSWORD=
DB_DATABASE=
DB_PORT=
DB_CONNECTION_LIMIT=
DB_CONNECTION_TIMEOUT=
```

| Option        | Value         | 
| ------------- |-------------| 
| DB_HOST      |  Database host    |
| DB_USER      |  Database username|
| DB_PASSWORD  |  Database password|
| DB_DATABASE  |  Database name    |
| DB_PORT      |  Connection port  |
| DB_CONNECTION_LIMIT| Maximum amount of connections. Maximum will not be used unless necessary.
| DB_CONNECTION_TIMEOUT| |

## General settings

```bash
LOG_LEVEL=
LOG_SIZE=
HOST=
PORT=
IMGURL=
MAX_POKEMON=
MIN_TTH=
IP_WHITELIST=
IP_BLACKLIST=
```
  
| Option        | Value         | 
| ------------- |-------------| 
| LOG_LEVEL | Logging level, can be `debug`, `info` or `error`.|
| LOG_SIZE | Maximum size of log file in Mb, default 25.|
| HOST |   Poracle host to listen on. |
| PORT | Poracle port to listen on. | 
| IMGURL | Source of monster icons. Trailing slash is important. [See originals](https://github.com/KartulUdus/PoracleJS/tree/master/src/app/util/images) |
| MAX_POKEMON | Biggest released pokemon_id. Needed for tracking batch tracking of mainimum/maximum IV.|
| MIN_TTH | Minimum amount of seconds for an alert to trigger|
| IP_WHITELIST | List of allowed IP's to send POST webhooks. Defaults to everything []|
| IP_BLACKLIST | List of blocked IP's to send POST webhooks. Defaults to nothing []|

## Locale settings

```bash
TIME_FORMAT=             # default: en-gb
TIME_STRING=             # default: LTS
ADDR_FORMAT=             # default: %S %n
PORACLE_LANGUAGE=        # default: en
```

| Option        | Value         | 
| ------------- |-------------| 
| TIME_FORMAT    | Sets 24 or 12h AM/PM time. use `"en-us"` for 12h time.|
| TIME_STRING | Time string format for disappear time. `LTS` for hours minutes and seconds `LT` for just hours and minutes.|
| ADDR_FORMAT | Format for the geocoded address. Can be any combination of : <br/>%P - country <br/>%p - country code <br/>%n - street number <br/>%S - street name <br/>%z - zip code <br/>%T - State  <br/>%t - state code|
| PORACLE_LANGUAGE | Translates pokemon for alerts and commands. Options are one of one of ['en', 'de', 'fr', 'ja', 'ko', 'ru'].|


## Reverse Geocoding Settings 

```bash
GEO_PROVIDER=            # default: poracle
GEO_KEY=
GEO_PROVIDER_URL=
```

| Option        | Value         | 
| ------------- |-------------| 
| GEO_PROVIDER| Geocoding provider and key (poracle, google, osm, nominatim)|
| GEO_KEY| Only [google](gmaps.html) requires a key|
| GEO_PROVIDER_URL| Optionally a Nominatim endpoint for local geocoding|

## Staticmap Settings
```bash
STATIC_PROVIDER=         # default: poracle
STATIC_KEY=

MAP_WIDTH=
MAP_HEIGHT=
MAP_ZOOM=

MAP_TYPE=
SPRITE_WIDTH=
SPRITE_HEIGHT=
```

| Option        | Value         | 
| ------------- |-------------| 
| STATIC_PROVIDER| Provider of {% raw %}{{{staticMap}}}{% endraw %} dts static map urls. (poracle, google, osm, mapbox)|
| STATIC_KEY| Your MapQuest, OSM or Google Key|
| MAP_WIDTH| Width in pixels of the static map.|
| MAP_HEIGHT| Height in pixels of the static map.|
| MAP_ZOOM | Zoom level of the static map.|
| MAP_TYPE| Should be "klokantech-basic" for static provider "poracle", "roadmap" for google static maps|
| SPRITE_WIDTH| Customize the sprites width added to the image (imgURL source used)|
| SPRITE_HEIGHT| Customize the sprites height added to the image (imgURL source used)|


## Telegram settings

```bash
TLG_ENABLED=          # default: false
TLG_TOKEN=["400000002:AAhdsjl_alkrhjfsqlkjEQ"]
TLG_ADMINS=["201234515"]
TLG_CHANNEL=
TLG_REGISTER=
TLG_IMAGES=           # default: true
TLG_LOCATION=         # default: true
TLG_STICKER=
```

| Option        | Value         | 
| ------------- |-------------| 
|TLG_ENABLED| Activate Telegram support|
|TLG_TOKEN| Your [Telegrambot Token](telegrambot.html). Has to be in [ "square.brackets.and.quotes" ]|
|TLG_ADMINS| Array of admin id's who can manage channels|
|TLG_CHANNEL| Channel name to register in|
|TLG_REGISTER| Channel ID to check users in|
|TLG_IMAGES | If telegram should send a sticker|
|TLG_LOCATION| If telegram should send a location|
|TLG_STICKER| Custom url for stickers, needs to be .webp. Default: https://raw.githubusercontent.com/KartulUdus/PoracleJS/master/src/util/images/telegram/|

### Usercheck

> PHP and composer is required!

It is possible to setup a automatic usercheck to unregister users that are not in a specific telegram group anymore. Enable it by setting `TLG_REGISTER` to the group ID of that specific group and giving admin/kick permissions to your bot. The next step is to install the required php packages by running `composer install`. When that is finished, try to run the command by hand: `php console Telegram:Member:Check` (make sure to be in Poracle root directory before running it). It should disable every member from your Poracle Database that is currently not in that group. To setup an automatic check, create a cron entry for it: 

```bash
0 * * * * cd /PATHTOYOUR/PoracleJS && php console Telegram:Member:Check > /dev/null 2>&1
```
This will run the check every hour.

## Discord settings

```bash
DISCORD_ENABLED=      # default: true
DISCORD_TOKEN=["NTM2Mj11111111111111111111.222222222222222xVTr1s"]
ADMINS=["222742859059560458", "353901047493951488"]
REGISTER_CHANNEL=     # default: general
REGISTER_ROLE=
PREFIX=               # default: !
TYPE_REACT=           # default: false
LIMIT_SEC=
LIMIT_MESSAGES=
IV_COLORS=
```

| Option        | Value         | 
| ------------- |-------------| 
|DISCORD_ENABLED| Activate Discord support|
|DISCORD_TOKEN | Your [Discordbot Token](../discordbot.html). Has to be in [ "square.brackets.and.quotes" ]|
|ADMINS| List of discord user id's that can register channels and run admin commands.|
|REGISTER_CHANNEL | The text channel where registering `!poracle` is possible. |
|REGISTER_ROLE| Role name that automatically registers or unregisters the user to !poracle|
|PREFIX| Prefix for all discord `!commands`|
|TYPE_REACT| `true` or `false`. If true, bot will react to alarms with the type of that alarmed monster.|
|LIMIT_SEC| Amount of seconds during which a user can only receive `limitamount` alerts |
|LIMIT_MESSAGES| Amount of alerts that a user can receive during `limitsec` seconds |
|IV_COLORS| A list of css style hex colors for iv quality.|

**IV colors**

There must be 6 colors defined, from worst IV to best.

The Colors are defined as you would in a html or css file: #rrggbb eg: #ff0000 for red.

The tiers of IV colors are as follows:

  | Min IV      | Max IV      | Default color  |
  | ----------- | ----------- | -------------- |
  | 0 %         | 24.9 %      | Gray   #9D9D9D |
  | 25 %        | 49.9 %      | White  #FFFFFF |
  | 50 %        | 81.9 %      | Green  #1EFF00 |
  | 82 %        | 89.9 %      | Blue   #0070DD |
  | 90 %        | 99.9 %      | Purple #A335EE |
  | 100 %       | 100 %       | Orange #FF8000 |

## Commands

Any command name can be renamed in the config file.

```bash
CMDPORACLE=
CMDAREA=
CMDBACKUP=
CMDCHANNEL=
CMDEGG=
CMDHELP=
CMDLODCATION=
CMDPVP=
CMDQUEST=
CMDRAID=
CMDRESTORE=
CMDSTART=
CMDSTOP=
CMDTRACK=
CMDTRACKED=
CMDUNREGISTER=
CMDUNTRACK=
CMDVERSION=
CMDWEBHOOK=
```

This does **NOT** rename command properties such as `remove`, `everything` or any of the genders.

## Weather 

Poracle can add a warning to a notification when a mon will change its IV because of a weatherchange. That weather prediction is 90% save and based on data from Accuweather. An API key is required!

```bash
WEATHER_APIKEY=
```

| Option        | Value       | 
| ------------- |-------------| 
|WEATHER_APIKEY| AccuWeather API Key|

When you are done with your config, you can make sure that it's a [valid JSON format here](https://jsonlint.com/)
