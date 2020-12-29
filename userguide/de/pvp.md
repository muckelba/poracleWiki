---
title: PvP
nav_order: 5
layout: default
parent: German
grand_parent: v3 Userguide
---

# PvP-Filter
Abschließend gib es in unserer Poracle-Version die Option nach bestimmten PvP-Rängen von bestimmten Pokémon zu filtern.  
Befehle dafür beginnen mit **`/pvp`**.  
Diese Befehle können sich genauso wie die "/track"-Befehle auf ein oder mehrere Pokémon, oder auf alle (everything) Pokémon beziehen.  
Dabei muss sich durch **`league1500`** oder **`league2500`** zwischen den 3 Verschiedenen PvP-Ligen entschieden werden. Wird keine Liga angegeben, wird die Meister-Liga gewählt.
Zudem muss sich entschieden werden, ob man jeweils nur das beste Pokémon oder aber z.B. die besten 5 gemeldet bekommen möchte. Dies erfolgt durch die angabe von **`maxrankX`**.  

Einige Beispiele:
**`/pvp bisaflor league1500 maxrank1`**  
Erzeugt die Einträge:  
Bisasam, Bisaknosp, Bisaflor; MaxLvl21; Stats0/14/11, also alle Pokémon, die das Potential haben (evtl. nach Entwicklung), ein perfektes Bisaflor zu werden.

**`/pvp +Glumanda league1500 maxrank2`**  
Erzeugt die Einträge:  
Glumanda; Maxlvl40; Stats15/15/15  
Glumanda; Maxlvl40; Stats14/15/15  
Glumanda, Glutexo; Maxlvl40; Stats0/14/14  
Glumanda, Glutexo; Maxlvl40; Stats0/13/15  
Glumanda, Glutexo, Glurak; Maxlvl20; Stats0/13/15  
Glumanda, Glutexo, Glurak; Maxlvl20; Stats0/15/13  

Ein Plus(+) vor dem Pokémon schließt die gesamte Pokémon-Familie mit ein. Daher werden 6 Einträge zu Glumanda erzeugt die 2 besten für Glumanda selbst, 2 für Glutexo und 2 für Glurak.

Alle PvP-Befehle können so wie "/track"-Befehle um Distanz(d) und Zeit(t) ergänzt werden. 
