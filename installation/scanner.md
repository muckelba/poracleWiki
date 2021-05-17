---
title: Scanner setup
nav_order: 4
layout: default
parent: Installation
---

# Configuring your scanner

You will need to set your scanner up to send webhooks to Poracle.

## MAD

Alter your config.ini file

```
# webhook
######################
webhook                     # Activate support for webhook
webhook_url: http://127.0.0.1:4201    # webhook endpoint (multiple seperated by comma)
#
```

This configures all webhooks to be sent to Poracle.  In the case that you are
using pvpHelper to send Pokemon to Poracle then you will need to exclude monsters - like this:

```
# webhook
######################
webhook                     # Activate support for webhook
webhook_url: [raid gym weather pokestop quest]http://127.0.0.1:4201             # webhook endpoint (multiple seperated by comma)
#
```

## RDM

(to complete)
