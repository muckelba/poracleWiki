Discord support uses a bot (see [Bot](../discordbot.md) on how to configure) to send alerts
to users. It can also use this bot to message channels, or you can use a webhook.

# User registration

Users can be registered with poracle using a 'call command' - by default `!poracle` or
automatically when assigned a specific role.

# Webhook or Bot for channels?

Adding a channel to poracle through a bot is easy.  Simply go into the channel and issue 
`!channel add` - you will then be able to send all the normal tracking commands.
All messages will be sent from the Poracle Bot that you configured.

Webhooks are slightly more complicated to manage, but have the advantage that you can
override the name of the sender and avatar picture for each message.

Existing webhooks can be registered as a channel using:
`!channel add http://discord.com/webhookurl namemychannel` - note that the *name* prefix is a parameter title and
an important part of the command.
You then can add trackings by sending DM to Poracle and including the name designator.

`!track everything iv100 namemychannel`

If you don't have a webhook created already, poracle can add one using the `!webhook` command
- eg `!webhook create`.  There is a combination command `!webhook add`which adds a hook and
registers the channel for receiving webhooks. By default the name with be the name of the
channel but - you can specify an alternative name using `name` as with channel add above.
  
# Custom Emoticons

<insert text here>

# Channel auto creation

The `!autocreate` command can create a category and channels for your new area automatically.  Create a file channelTemplate.json in your config directory (example in defaults) with a definition.  Configurable fields can be use starting with {0} which can be used for whatever you want - area, language, etc.
Poracle can register the channels (or leave as text only), or create a webhook and set that up.  It can also provide some basic role settings (thanks petap0w!)
Poracle needs to know the guild to work on; so if you execute it in a channel it can work this out or specify with the guild.
Example commands:

* `!autocreate newSection newyork` - would execute the below with {0} being newyork
* `!autocreate guild123456 newSection newyork french` - would execute the below on guild id 123456 with {0} being newyork and {1} being french (although this is not used in the example)

Note that as soon as you use roleIds this template becomes guild specific so careful use of this feature is needed if poracle is in multiple guilds (see petap0ws comment below on how it can be used)

```[
  {
    "name":"newSection",
    "definition":{
      "category":"{0} Pokemon",
      "channels":[
        {
          "channelName":"{0}-iv100",
/*
          "roles":[
            {
              "id":"11111111111111111", "view": true, "viewHistory": true, "send": true, "react": true
            }
          ],
*/
          "topic": "Hundos for {0}",
          "controlType":"bot",
          "commands":[
            "area add {0}",
            "track everything iv100"
          ]
        },
        {
          "channelName":"{0}-UltraRares",
          "controlType":"webhook",
          "commands":[
            "area add {0}",
            "track everything rarityultra-rare maxrarityultra-rare"
          ]
        },
        {
          "channelName":"{0}-Raids",
          "controlType":"webhook",
          "commands":[
            "area add {0}",
            "egg level5 level6 clean",
            "raid level5 level6 clean"
          ]
        }
      ]
    }
  }
]```
