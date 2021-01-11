---
title: Geocoding
nav_order: 5
layout: default
parent: v4
---

# Geocoding
{% raw %}
Poracle supports four different geocoding services for displaying addresses in your DTS by using `{{addr}}`, `{{streetNumber}}`, `{{streetName}}`, `{{zipcode}}`, `{{country}}`, `{{countryCode}}`, `{{city}}`, `{{state}}`, `{{stateCode}}` and `{{neighbourhood}}`.
{% endraw %}

## Poracle

That's the public hosted nominatim server. Completely free and without ratelimits. **Currently not available**

## Nominatim

That's the option for a self hosted nominatim server. Read more about it [here](https://github.com/mediagis/nominatim-docker).


## Google Maps

### API Key

Please log in to [Google Developers console](https://console.developers.google.com/) and make sure you have the following API's enabled:  
   
* Google Maps Javascript API 
* Google Maps Geocoding API
* Google Reverse Geocoding API

You can test if your API key manually by adding your key to the below urls:  

### Test

#### Geocoding

```
https://maps.googleapis.com/maps/api/geocode/json?address=Tallinn+Estonia&key=YOURKEYHERE
```  

#### Reverse Geocoding

```
https://maps.googleapis.com/maps/api/geocode/json?latlng=59.432982,24.7535747&key=YOURKEYHERE
```


## OSM

OpenStreetMap offers a public nominatim server as well, but ratelimits very hard which makes it almost unuseable with PoracleJS.