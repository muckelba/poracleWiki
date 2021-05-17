---
title: !track
nav_order: 3
layout: default
parent: English
grand_parent: User Guide
---

## `!track` in detail

Note that some Pokemon are available from scanners without IV details. Poracle will treat these as having an IV
of -1 in filtering decisions - specifiying a minimum iv of 0 (ie iv0) will exclude these.

| Filter    | Example                         | Description  |
| --------- |:-------------------------------:| -----------:|
|           |`!track pikachu`<br>`!track 2 3 4` | No filters, tracks listed pokemon within an area you are tracking in.  Tracking of pokemon can be by name or pokedex number|
|d          |`!track pikachu d750`            | Tracks pikachu within 750 meters of your !location |
|iv         |`!track pikachu iv90`            | Tracks pikachu inside a tracked area with a minimum IV of 90%  |
|maxiv      |`!track pikachu maxiv0`          | Tracks pikachu with 0% IV   |
|weight     |`!track magikarp weight13130`    | Tracks "big" magikarp (13130 grams and higher)|
|maxweight  |`!track rattata maxweight2410`   | Tracks "tiny" rattata (2410 grams and lower)|
|male       |`!track rattata male`            | Tracks male rattata |
|female     |`!track pikachu female`          | Tracks female pikachu |
|everything |`!track everything iv90 level20` | Tracks eveything with a minimum IV of 90% level 20 and higher. |
|type|`!track dragon` | Track dragon type pokemon
|gen |`!track everything gen6 iv60`<br>`!track dark gen3 iv90` | *gen* is a filter so needs to be specified alongside 'everything' or types lists of pokemon. Tracks gen 6 pokemon with a minimum IV of 60% level 15 and higher. |
|atk, def, sta|
|maxatk, maxdef, maxsta|
|cp|
|form||
|t|
|rarity||1-6 or [ ... ultra-rare, unseen]|
|maxrarity|
    "rarity": {
        "1": "Common",
        "2": "Uncommon",
        "3": "Rare",
        "4": "Very-Rare",
        "5": "Ultra-Rare",
        "6": "Unseen"
    },
|greatcp|
|"

|clean|
|template|

# PVP

|Command|Usage|
|---|---|
|`!track snorlax great1`| for top 1 great league snorlax|
|`!track everything great1 greatcp1450`| for top 1 great league pokemon| maxing out at or above 1450CP|
|`!track snorlax ultra100`| for top 100 ultra league snorlax|
|`!track everything ultra1 ultracp2400`| for top 1 great league pokemon maxing out at or above 2400CP|

An example notification containing PVP information - you can see what this Eevee can become in Great and Ultra leagues in all its various forms


# Advanced options

|individually|`!track everything individually iv100` | Inserts a tracking entry for every single Pokemon rather than a single 'everything' entry. This allows you to do 'everything but..' by removing some afterwards|
