---
title: Profiles
nav_order: 3
layout: default
parent: English
grand_parent: User Guide
---

# Profiles
Profiles allow you to specify different tracking configurations for different times.
You create profiles with `!profile add` eg `!profile add home`.  You can list your profiles with `!profile list`

Note that to change tracking switch to a particular profile (eg `!profile home`, issue tracking, location or area commands and these will be set to the current profile.

But what about automatic change based on time of day?  You can do 
`!profile settime` _activationtimes_ - where the activationtimes are 
days of week & times to activate - eg 'mon9:15' or 'weekday17:00' or 
'weekend09'.  

Every 10 minutes Poracle will check if a profile was due to activate and will 
set it.
