---
title: PvP
nav_order: 5
layout: default
parent: English
grand_parent: Userguide
---

# PvP Filters
Finally, in our Poracle version you can filter specific Pokémon by their PvP rankings. 
Those commands start with **`/pvp`**. 
Just like the */track*-commands, these commands can refer to one or several Pokémon or to all Pokémon ("everything"). 
When you want to use PvP-commands, you have to decide on one of the 3 different PvP Leagues using **`league1500`** or **`league2500`**. If you do not enter a specific league, the system defaults to Master League. Additionally, you have to decide if you want notifications only for the one best Pokémon or e.g. for the best 5 Pokémon. You can do so by entering **`maxrankX`**. 

Some examples:
**`/pvp venusaur league1500 maxrank1`**  
Creates the following entries:  
Bulbasaur, Ivysaur, Venusaur; MaxLv21; Stats0/14/11, and all Pokémon that have the potential to become a perfect Venusaur (e.g. by evolving).

**`/pvp +Charmander league1500 maxrank2`**  
Creates the following entries:  
Charmander; Maxlvl40; Stats15/15/15  
Charmander; Maxlvl40; Stats14/15/15  
Charmander, Charmeleon; Maxlvl40; Stats0/14/14  
Charmander, Charmeleon; Maxlvl40; Stats0/13/15  
Charmander, Charmeleon, Charizard; Maxlvl20; Stats0/13/15  
Charmander, Charmeleon, Charizard; Maxlvl20; Stats0/15/13  

Putting a plus (+) before the Pokémon name includes the whole Pokémon family. Therefore, the system creates 6 entries for Charmander: the 2 best for Charmander itself, 2 for Charmeleon, and 2 for Charizard.

Just like "/track", all PvP-commands can be specified using distance (d) and time (t). 