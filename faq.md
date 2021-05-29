Some frequently (or not so frequently) asked questions

# Poracle is not listening

Testing poracle listens

`curl http://127.0.0.1:3030/health`

# How to pull request

git fetch origin pull/246/head:telegram
git checkout telegram

# PM2 warning on startup

```2|poracle  | WARNING: NODE_APP_INSTANCE value of '0' did not match any instance config file names.
2|poracle  | WARNING: See https://github.com/lorenwest/node-config/wiki/Strict-Mode
```

Create default-0.json in config folder containing

```{}```

# How does duplicate elimination work?

Pokemon: Encounter ID, Disappear Time Present, CP
Raid/Egg: Gym, Message End, Pokemon ID
Incident: Pokestop ID, IncidentExpiration
Quest: Pokestop ID, Rewards

