---
title: Filtering Options
nav_order: 3
layout: default
parent: English
grand_parent: v3 Userguide
---

# Filtering Options

## Basics
**`/stop` & `/start`**  
When you use the bot for the first time, you have to start it. If you stop the bot at some point and want to restart, you can do so using "/stop" and "/start".

**`/location`**  
You can choose your personal location using the location command. The command can be specified by coordinates or a postal address. You can check if the location has been applied correctly using the */tracked*-command. Afterwards, the location will be used for the filtering option 'distance'.

**`/area add` & `/area remove` & `/area list`**  
As an alternative to your personal location, you can also select preset areas. You can see which areas are available for your bot using the command `/area list`. The areas listed there can be added using `/area add *name*` and removed using `/area remove *name*`.

**`/tracked`**  
shows the current filtering settings, followed by specifications on the location, the selected areas and all filters referring to anything from [Pokémon](#pokémon) to [Rocket/Invasion](#rocketinvasion).


## Pokémon
This section lists all filtering options for tracking Pokémon. Every command must refer to at least one Pokémon, but all other components can be chosen or left out as desired.

**`/track pikachu d1000 iv20 maxiv30 wp400 maxwp500 level6 maxlevel7 atk8 maxatk9 def8 maxdef9 sta8 maxsta9 t10 male/female/genderless`**

**`/track`**  
All commands to receive Pokémon notifications start with "/track". Using "/untrack [...]", you can remove the respective commands again. Note that you can only remove all tracking commands for a single Pokémon or a command for all Pokémon at the same time.

**`pikachu`**  
This part of the command indicates which Pokémon the command refers to. It is possible to name one or more Pokémon using their Pokédex numbers or name (English or German), separated by space. You can track all Pokémon using "everything", or one whole generation of Pokémon using "genX".

**`d1000`**  
You can use the geo location to filter if a Pokémon notification will be of interest for you. If one or more areas have been selected, as described in the [Basics](#basics), you will be notified about all Pokémon within those areas with the selected stats. Alternatively, you can select a personal location. The filtering option "dXXXX" refers to that location and sets the maximum distance from this location in meters. You can use area and location at the same time. Notifications will refer to both, the whole area and the whole radius of the location.

![](../../assets/Location.png)
If a user has chosen the location S, uses the distance D and has added area A, they receive notifications for X1 as a part of area A, notifications of X3 as it is included in the distance radius around S, and notifications for X2 for both reasons. They will not, however, receive notifications for X4, as that point lies outside both, the area and the distance radius. 

**`iv20 maxiv30`**  
"ivX" indicates the minimum IVs the Pokémon must have to warrant a notification. If you do not set an "ivX", the minimum is set to iv0 automatically.
"maxivX" indicates the maximum IVs a Pokémon may have to warrant a notification. If you do not set a "maxivX", the maximum is set to iv100 automatically. 

Examples:  
**`/track pikachu iv100`** - sends notifications for all Pikachu with 100 IV. 
**`/track pikachu maxiv0`** - sends notifications for all Pikachu with 0 IV.  
**`/track pikachu miniv50 maxiv60`** - sends notifications for all Pikachu with IVs between 50% and 60%.

**Note:** IV specifications will be rounded to whole numbers. A Pokémon classified as IV98 actually has 44 of 45 possible IV points (15atk,15def,15sta), which are 97,77% mathematically.  Technically, IV97,77 should not be included in the IV range 98 and up. But since Poracle rounds the values, 97,77% falls into the IV98+ range, while 93,33% would not fall into the IV94+ range. 

**`wp400 maxwp500`**  
"wpX" indicates the minimum CP a Pokémon must have to warrant a notification. If you do not set a "wpX", the minimum is set to wp0 automatically.
"maxwpX" indicates the maximum CP a Pokémon may have to warrant a notification. If you do not set a "maxwpX", there is no upper limit.

**`level6 maxlevel7`**  
"levelX" indicates the minimum level a Pokémon must have to warrant a notification. If you do not set a "levelX", the minimum is set to level 0 automatically. 
"maxlevelX" indicates the maximum level a Pokémon may have to warrant a notification. If you do not set a "maxlevelX", there is no upper limit.

**`atk8 maxatk9`**  
"atkX" indicates the minimum attack value a Pokémon must have to warrant a notification. If you do not set a "atkX", the minimum is set to atk0 automatically. 
"maxatkX" indicates the maximum attack value a Pokémon may have to warrant a notification. If you do not set a "maxatkX", the maximum is set to atk15 automatically.

**`def8 maxdef9`**  
See section on atk. Replace atk with def.

**`sta8 maxsta9`**  
See section on atk. Replace atk with sta.

**`t10`**  
Indicates the minimum time left for a notification until the Pokémon despawns. Some notifications come in rather late, with 2 minutes time left, for example. Since these Pokémon can likely not be reached in time, you can deactivate notifications for them.

**`male/female/genderless`**  
This way, you can filter by gender classification. This is especially useful if you are looking for a Combee that can evolve, for example. You would only have to look for the female form.

Additionally to the Pokémon names, Poracle also knows various names for specific forms, e.g. to look only for Alola-Pokémon. You can find an explicit list in the section [Pokémon Forms](#special-form_names).

You can create several entries for a single Pokémon. 
For example, you could use two commands to receive notifications for Pokémon with maximum IV0 and Pokémon with minimum IV100, both. 

Important: to check if a /track command works as intended, use the command **`/tracked`** whenever you need to. This way, the bot will show you all filter settings it is currently using. 

## Quests
All quest commands start with **`/quest`** and can be removed again using **`/quest remove`**. Quest commands can include the component for distance described in [Pokémon](#pokémon).

### Pokémon
**`/quest Pikachu`** - sends notifications for all quests with Pikachu as a reward. 
**`/quest all pokemon`** - sends notifications for all quests with a Pokémon as a reward. 
**`/quest gen1`** - sends notifications for all quests with a first-generation Pokémon as a reward.

### Items  
**`/quest all items`** - sends notifications for all quests with items as a reward. 
**`/quest item rare candy`** - sends notifications for all quests with rare candy as a reward.  

| Written Command | Item Name |   
|:-----------|:-------------|  
|"Poke Ball",|  Poké Ball |  
|"Great Ball",  | Great Ball |  
|"Ultra Ball",  | Ultra Ball |  
|"Master Ball",  | Master Ball |  
|"Premier Ball",  | Premier Ball |  
|"Potion",  | Potion |  
|"Super Potion",  | Super Potion |  
|"Hyper Potion",  | Hyper Potion |  
|"Max Potion",  | Max Potion |  
|"Revive",  | Revive |  
|"Max Revive",  | Max Revive |  
|"Lucky Egg",  | Lucky Egg |  
|"Incense Ordinary",  | Incense |  
|"Incense Spicy",  | n/a |  
|"Incense Cool",  | n/a |  
|"Incense Floral",  | n/a |  
|"Troy Disk",  | Lure Module |  
|"Troy Glacial Disk",  | Glacial Lure Module |  
|"Troy Mossy Disk",  | Mossy Lure Module |  
|"Troy Magnetic Disk",  | Magnetic Lure Module |  
|"X Attack",  | X Attack |  
|"X Defense",  | X Defense |  
|"X Miracle",  | X Miracle |  
|"Razz Berry",  | Razz Berry |  
|"Bluk Berry",  | n/a |  
|"Nanab Berry",  | Nanab Berry |  
|"Wepar Berry",  | n/a |  
|"Pinap Berry",  | Pinap Berry |  
|"Golden Razz Berry",  | Golden Razz Berry |  
|"Golden Nanab Berry",  | Golden Nanab Berry |  
|"Silver Pinap Berry",  | Silver Pinap Berry |  
|"Special Camera",  | Special Camera |  
|"Incubator Basic Unlimited",  | Egg Incubator Unlimited |  
|"Incubator Basic",  | Egg Incubator |  
|"Incubator Super",  | Super Incubator |  
|"Pokemon Storage Upgrade",  | Pokémon Storage Upgrade |  
|"Item Storage Upgrade",  | Bag Upgrade |  
|"Sun Stone",  | Sun Stone |  
|"Kings Rock",  | King's Rock |  
|"Metal Coat",  | Metal Coat |  
|"Dragon Scale",  | Dragon Scale |  
|"Up Grade",  | Up-Grade |  
|"Sinnoh Stone",  | Sinnoh Stone |  
|"Unova Stone",  | Unova Stone |  
|"Fast TM",  | Fast TM |  
|"Charged TM",  | Charged TM |  
|"Rare Candy",  | Rare Candy |  
|"Free Raid Ticket",  | Battle Pass |  
|"Paid Raid Ticket",  | Premium Battle Pass |  
|"Legendary Raid Ticket",  | EX Raid Pass |  
|"Star Piece",  | Star Piece |  
|"Friend Gift Box"  | Gift |  

**Note:** The system only supports English names for quest items. You can select all items available in the game data. This does not mean, however, that all those items are actually available in quests or at all in the game.

### Stardust
**`/quest stardust`** - all quests with stardust as a reward.
**`/quest stardust500`** - all quests with at least 500 stardust as a reward. 


## Raids
There are two different kinds of Raid notifications. You can receive notifications when Raid Eggs appear or when a certain Raid Boss hatches. 
For Eggs, your command starts with */egg*, while the command for the Raid Boss starts with */raid*.
Consequently, you have to use */raid*-commands to receive notifications for specific Pokémon. 
**`/raid Snorlax`** - sends notifications for all Snorlax Raids. 
**`/raid gen1`** - sends notifications for all raids with a first-generation Pokémon (Kanto).

Additionally, you can set the following filters for */raid*-commands and */egg*-commands (most of the filters can be combined freely):
**`/raid(/egg) level2`** - sends notifications for all Tier 2 Raids or Eggs (cannot be combined with a filter for specific Pokémon!)
**`/raid(/egg) d1000`** - Raids can be filtered by location.
**`/raid(/egg) ex`** - sends notifications only for Raids at Gyms that are currently labeled as EX Raid Gyms.
**`/raid(/egg) instinct/valor/mystic/harmony`** - sends notifications only for Raids at Gyms currently controlled by the selected team.
**`/raid(/egg) everything`** - sends notifications for all Raids/Eggs.

**`/egg remove`** or **`/raid remove`** removes all filters for Raids and Eggs. It can also refer to single Raid Tiers and Pokémon, e.g **`/raid remove Snorlax`**.

## Rocket/Invasion
Currently, scanning Rocket-invaded PokéStops only happens passively. This means that the PokéStops are not actively approached, just detected by the radar. At any point where a scanner is doing a job of any kind, e.g. scanning a Pokémon, it collects information about invaded Stops in the surrounding area.
Included is information on the location of the grunt, their quote, and their gender. There is a specific set of Pokémon assigned to every combination of quote and gender. This set consists of different Pokémon which can be encountered as invasion reward at different odds.
Since the workers never actively engage in a Rocket battle, they do not know exactly which Pokémon will be the reward. Consequently, you cannot filter for specific Pokémon in Poracle, but only for type and gender.

All invasion-commands start with */invasion*. 
You can remove all filtering settings for invasions using **`/invasion remove`**. 
**`/invasion`** - sends notifications for all invaded Stops. 
*/invasion*-commands can be specified by both areas and distances (d). 
Additionally, you can filter by all 16 available Pokémon types (English names) and gender.

| Written Command | Meaning/Result |   
| :-----------|:-------------|  
|"normal"| Tracks invasions with a chance to get a normal type Pokémon  |  
|"fire"| Tracks invasions with a chance to get a fire type Pokémon  |  
|"fighting"| Tracks invasions with a chance to get a fighting type Pokémon  |  
|"water"| Tracks invasions with a chance to get a water type Pokémon  |  
|"flying"| Tracks invasions with a chance to get a flying type Pokémon  |  
|"grass"| Tracks invasions with a chance to get a grass type Pokémon  |  
|"poison"| Tracks invasions with a chance to get a poison type Pokémon  |  
|"electric"| Tracks invasions with a chance to get an electric type Pokémon  |  
|"ground"| Tracks invasions with a chance to get a ground type Pokémon  |  
|"psychic"| Tracks invasions with a chance to get a psychic type Pokémon  |  
|"rock"| Tracks invasions with a chance to get a rock type Pokémon  |  
|"ice"| Tracks invasions with a chance to get an ice type Pokémon  |  
|"bug"| Tracks invasions with a chance to get a bug type Pokémon  |  
|"dragon"| Tracks invasions with a chance to get a dragon type Pokémon  |  
|"ghost"| Tracks invasions with a chance to get a ghost type Pokémon  |  
|"dark"| Tracks invasions with a chance to get a dark type Pokémon  |  
|"steel"| Tracks invasions with a chance to get a steel type Pokémon  |  
|"fairy"| Tracks invasions with a chance to get a fairy type Pokémon  |  
|"mixed"| Tracks invasions with an undetermined type | 
|"male"| Tracks male invasions  | 
|"female"| Tracks female invasions  | 

*Note:* You can combine several filters/types. E.g.: **`/invasion fire water ice male`** - tracks all male invasions with either a fire type, water type, or ice type Pokémon as a reward.
