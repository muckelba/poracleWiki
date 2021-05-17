---
title: Commands (Admin)
nav_order: 2
layout: default
parent: Operation
---

Note that the `!` prefix is used throughout this page; simply swap this for '/' for telegram, 
or however you have configured your discord prefix

# userlist

The `!userlist` command shows a list of registered users. These user identities can be used
for other administrative commands.  For discord you can often get the ID of a user by
right clicking and selecting *copy id*.

# backup, restore

# community

Allows you to apply community restrictions to a channel. See [Area security](areasecurity.md)
for more details

# unregister

This command allows a user to unregister themselves (not an admin though!) - but admins
can also user it to unregister users using their user id (from userlist)

# disable, enable

These are admin commands to disable or enable a user. Users will not be able to use Poracle
all the time they are disabled.  They will be marked in the `!userlist` above.

# apply *run commands across multiple channels*

The apply command can be to issue commands against multiple channels, by ID or by name. 
Remember `!userlist` will list your users and channels if you need to remember what's going on. You can use % wildcards for matching channel names.

Use the | separator to indicate the end of the channel list and start of commands, and between commands. You need the spaces!

`!apply 34455322334 234442223432 | track bulbasaur`

`!apply %events | untrack everything | track fletchling iv95`

# channel

Allows you to register a telegram channel, or a discord webhook.  See [Telegram](telegram.md)
or [Discord](discord.md) pages for details specific to the endpoint

# autocreate 

Discord only, this allows you to create categories and channels automatically.  See [Discord](discord.md)

# webhook

Discord only, this allows you to create categories and channels automatically.  See [Discord](discord.md)

# userXXXX *run s a user*

Any user command can have the `user` parameter to specify a user to run it as. This allows
you an easy way to see a user's tracking, for example.
