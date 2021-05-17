---
title: DTS Templates (Advanced)
nav_order: 6
layout: default
parent: Configuration
---


Handlebars functions

{{numberFormat xx 2}}
{{calculateCp}}
{{pokemonBaseStats}}
{{getPowerUpCost}}
{#getPowerUpCost 5 10}}Candy - {{candy}} Stardust - {{stardust}}{{/getPowerUpCost}}

{{map}}

{{concat}}
{{pad0}}
{{map}}

There's a new mapping function.  Define a map in the customMaps folder like this --
```json5
{
  "name": "raidCounters",
    "map": {
        "144": {
            "trainers": "2",
            "counters": "Rampardos, Shadow Tyranitar, Rhyperior, Terrakion, Shadow Omastar & Tyranitar"
        },
        "145": {
            "trainers": "3",
            "counters": "Shadow Mamoswine, Shadow Tyranitar, Rhyperior, Shadow Mewtwo, Mega Abomasnow & Mamoswine"
        },
        "146": {
            "trainers": "2",
            "counters": "Shadow Tyranitar, Rampardos, Rhyperior, Terrakion, Shadow Omastar & Shadow Aerodactyl"
        }
    }
}
```
And you can then use it in your DTS to map from anything to anything - eg in this example pokemon Id maps to trainers and the counters for advanced raid displays.  You use it like this: {{#map 'raidCounters' pokemonId}}Trainers needed: {{trainers}} Best counters: {{{counters}}}{{/map}}. If you have a single value you map to you can just use {{map 'name' value}} rather than having subvariables.  I hope people will come up with some imaginative mappings and share them (we have a defaults/customMaps folder so we can ship some cool ones!)

{{... calculate stardust }}

handlebars helpers

{{#each}}

eg {{#each matched}}{{map 'arealist' this}}{{/each}}

{{compare}}


{{join}}

{{eq}}

