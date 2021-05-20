---
title: Other Settings (Advanced)
nav_order: 6
layout: default
parent: Configuration
---
### Pokemon aliasing

The `pokemonAlias.json` file provides a mechanism for aliasing commonly mis-spelt pokemon.
It currently has an English focus, but you can update your local copy.  Contributions for
good additions will certainly be considered for more widespread distribution so please
share

### Shortened URLs

Wrap in `<S<` and `>S>` for Poracle to pass the URL through a shortener
(currently only *xxxxx* is supported)

### Changing discord emoticons

First you'll need to add your custom emoji to your server. I just found mine by searching in google. Then you need to find the ID of each emoji. Yours will be different ID to mine.

Custom emotes are represented as formatted text, similar to how mentions are just formatted text.  The format is
`<:name:id>` Example `<:bug:236227272899902>` is a custom emoji named `bug` with the id `236227272899902`.

You can get a custom emoji ID by right clicking the custom emoji and copying its URL, with the ID being the
image filename.

Example translation file:

```json
{
    "🐛":"<:bug:yourid>",
    "🌑":"<:dark:yourid>",
    "🐲":"<:dragon:yourid>",
    "⚡":"<:electric:yourid>",
    "🦋":"<:fairy:yourid>",
    "👊":"<:fighting:yourid>",
    "🔥":"<:fire:yourid>",
    "🐦":"<:flying:yourid>",
    "👻":"<:ghost:yourid>",
    "🌿":"<:grass:yourid>",
    "⛰️":"<:ground:yourid>",
    "❄":"<:ice:yourid>",
    "⭕":"<:normal:yourid>",
    "☠":"<:poison:yourid>",
    "🔮":"<:psychic:yourid>",
    "🗿":"<:rock:yourid>",
    "🔩":"<:steel:yourid>",
    "💧":"<:water:yourid>"
}
```

The bot can use emojis of any server it's invited to. So as long as your bot is on each server you can just have the emoji added to just one server.

This approach does cause a problem if you parallel run with Telegram because these translations are system-wide.

### PVP Scanner

### Facebook

Facebook messenger can be used with an add-on - see third party apps.  Note that Facebook like to ban
accounts that use unofficial bots so this is only of use for low volume groups (like hundos) rather than
a full interactive experience.

### Delegated Administration

You can configure that certain users are able to make changes to the tracking in channels, groups, or on webhooks.

For discord this looks like this:  The ID number in channel tracking can be a guild (can change tracking for all channels in a guild), a category (all channels in a category), or an individual category.
The admin

```json
     "delegatedAdministration": {
             "channelTracking": {
                "794678214236438569": [ "745735260020539513" ]
            },
            "webhookTracking": {
                "poracle-test": ["726564415431770202" ]
            }
        },
```
For telegram, the channelTracking can be the name of a channel or the id number of a group.

### Reconciliation

The reconciliation that runs every <n> hours can now do even more!
If the telegram option registerOnStart is set then this is run on a /start message (which is sent automatically by the telegram client). This means that users who are in the appropriate feeder channels will be registered on a /start and don't need to do a /poracle.

```json
"reconciliation": {
    "discord": {
        "updateUserNames": false,                // Follow discord username changes
        "removeInvalidUsers": true,              // Whether users who lose roles should be de-registered
        "registerNewUsers": false,               // Whether users who are granted roles are auto-registered
        "updateChannelNames": true,              // Whether channel names are kept in sync
        "updateChannelNotes": false,             // Whether channel notes are updated to contain guild name / category
        "unregisterMissingChannels": false       // Whether channels that are deleted from discord are removed from database
    },
    "telegram": {
        "updateUserNames": false,                // Follow telegram username changes
        "removeInvalidUsers": true               // Whether users are automatically removed
    }
},
```
