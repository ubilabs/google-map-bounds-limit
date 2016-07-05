# google maps bounds limit

This module limits the map movement and zooming functionality of a provided google maps instance to a given bounds value.

## Installation

```sh
npm install google-map-bounds-limit
```
## How to use

```js
import limitMap from 'google-map-bounds-limit';

const map = new google.maps.Map(...);
const maxBounds = new google.maps.LatLngBounds(
  new google.maps.LatLng(-40, -90),
  new google.maps.LatLng(38, 70)
);

limitMap(map, maxBounds);
```

## Notes
- To prevent zooming we currently use `google.maps.Map.setOptions({minZoom: <value>})`. If you instantiate your map with a `minZoom` option, it might be overwritten.
- For a "global" limit use these bounds:
```js
const maxBounds = new google.maps.LatLngBounds(
  new google.maps.LatLng(-85, -175),
  new google.maps.LatLng(85, 175)
);
```
The actual lat/lng limits (+/-90 and +/-180) won't be reached.

## Resources
- [**LatLngBounds Class** (Google Maps JS API Reference)](https://developers.google.com/maps/documentation/javascript/reference#LatLngBounds)
- [**LatLng Class** (Google Maps JS API Reference)](https://developers.google.com/maps/documentation/javascript/reference#LatLng)
