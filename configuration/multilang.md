---
title: Internationalisation
nav_order: 8
layout: default
parent: Configuration
---

# Introduction

Poracle has first class internationalisation support including every user
string translatable, and all notifications being able to be customised.

## Single language

```json
"general": {
  "locale": "en", // default locale for Poracle - eg en, fr, de, it, ru
}  
```

Change the locale in your local.json file - this will cause Poracle to pick up
the translation file in config/locale - eg fr.json.  If you want to change
any translations, please see the customisation section later.

## Multi-language


### Configuration

```json
     "availableLanguages": {
        "en": {"poracle": "poracle", "help": "help" },
        "de": {"poracle": "dasporacle", "help": "hilfe" },
        "fr": {"poracle": "leporacle", "help": "aide" }
    },
```

### Customising the translation

* Create a file called `custom.<locale>.json` - eg `custon.en.json` in your config
directory to override standard configuration

### Translating your own language
