---
title: Staticmaps
nav_order: 6
layout: default
parent: v4
---

# Staticmaps
{% raw %}
Poracle supports five different staticmaps services for displaying little maps below your alarms by using `{{{staticmap}}}`. If you are using Telegram, you can set `webpage_preview` to True and put `[\u2007]({{{staticmap}}})` infront of your text to have an embedded staticmap.
{% endraw %}

## Poracle

That's the public hosted tileservercache server. Completely free and without ratelimits. **Currently not available**

## TileServerCache

That's the option for a self hosted TileServerCache server. Read more about it [here](https://github.com/123FLO321/SwiftTileserverCache). 

You need to copy the four templates located in `tileservercache_templates/` into the `Templates/` directory of your Tileserver.


## Google Maps

### API Key

Please log in to [Google Developers console](https://console.developers.google.com/) and make sure you have the following API's enabled:  
   
* Google Maps Javascript API 
* Google Static Maps API  

### Test

You can test if your API key manually by adding your key to the below urls:  

```
https://maps.googleapis.com/maps/api/staticmap?center=59.432982,24.7535747&markers=color:red|59.432982,24.7535747&maptype=roadmap&zoom=15&size=250x175&key=YOURKEYHERE
```  

## Mapquest

### API Key

Go to [the Mapquest website](https://developer.mapquest.com/), click on `Get your Free API Key`, log in and copy the Key. The limit is 15,000 tiles a month.

### Test

```
https://www.mapquestapi.com/staticmap/v5/map?locations=59.432982,24.7535747&size=250x175&defaultMarker=marker-md-3B5998-22407F&zoom=15&key=YOURKEYHERE
```

## Mapbox

### API Key

Go to [the Mapbox website](https://www.mapbox.com/), click on `Start mapping for free`, log in and copy the Key. The limit is 50,000 a month.

### Test

```
https://api.mapbox.com/styles/v1/mapbox/streets-v10/static/url-https%3A%2F%2Fi.imgur.com%2FMK4NUzI.png(59.432982,24.7535747)/59.432982,24.7535747,15,0,0/250x175?access_token=YOURKEYHERE
```