MapboxMap
==========

**Notice**: this never was a full-feature library, merely a layer on top of Mapbox JS SDK. For a better, more full fledged solution, try [react-leaflet](https://github.com/PaulLeCam/react-leaflet) (in conjunction with the Mapbox [Maps API](https://www.mapbox.com/api-documentation/#maps) in our case).

```
npm install react-mapboxmap
```

```js
var React = require('react'),
    MapboxMap = require('react-mapboxmap');

var Master = React.createClass({
  render: function() {
    return (
      <div className="container">
        <MapboxMap
          mapId="mapbox.comic"
          zoomControl={false}
          center={[59.907433, 30.299848]} zoom={17}
          onMapCreated={this._onMapCreated}/>
      </div>
    );
  },
  _onMapCreated: function(map, L) {
    var marker = new L.Marker(new L.LatLng(59.907433, 30.299848));
    map.addLayer(marker);
  }
});
```

Attributes
-----------

* `mapId` or `src` -- either a map id (`examples.map-foo`), a comma-separated list of ids, a URL to TileJSON (`https://api.tiles.mapbox.com/v3/examples.map-0l53fhk2.json`) or a TileJSON object

* `onMapCreated(map, L)` -- a callback for furter customization. Params:

    - `map` -- the map object
    - `L` -- the Leaflet.js instance used to create the map (Mapbox.js included)

License
--------

MIT
