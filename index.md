---
layout: home
title: Home
nav_order: 1
has_toc: true
---

![logo](assets/PoracleJSWiki.png)
# Poracle Documentation

PoracleJS is a high performance notification system that works with MAD or RDM.  It can send 
end-user configurable alerts to users as well as populating channels with information about Pokemon Go.

It supports sending messages about wild spawns, eggs, raids, field research (quests), invasions, lures, and nests

Some features include:
* Support for Discord and Telegram (simultaneously if required)
* Support for RDM and MAD
* Web user interface to allow end-users to configure tracking (PoracleWeb)
* High performance - some users handling more than 20M events per day
* Automatic cleaning of out-of-date messages
* Fully configurable alert styles, including multiple templates for different uses
* Multiple servers
* Fully multi-lingual. Poracle has translations for most major languages and can be configured to allow end-users
    to switch language.
* User switchable profiles to support different tracking requirements based on time of day
* Support for custom map tiles, including pre-generation of tiles and "multi-maps" (eg including both map overview and satellite imagery)
* In game weather forecast, and notification when weather changes affect tracked Pokemon
* Multiple community (area) security allowing control over different areas with different security
* Templated creation of alert-channels to allow easy support of new areas
* Rarity calculation 

## Older versions

Head over to [v3](v3) or [v4](v4) for the respective version you are using.

## Current Situation
- Geocoding and Staticmaps served by `poracle` are not not working as the public server is not available. You can host them on your own:
    - [Geocoding](https://github.com/mediagis/nominatim-docker)
    - [Tileserver](https://github.com/123FLO321/SwiftTileserverCache)
