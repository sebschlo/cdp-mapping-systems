# Assignment 02 - Geoprocessing

### Sebastian Schloesser

## Exporing Data Sets

I've started exploring with the following data sets:
* My Google Timeline data
* Metadata from my Photos library

My created geoJSON file is a h3 binning of New York City, where each bin contains counts for trips started by type, as described by the Google Timeline dataset. The types include:
* cycling
* flying
* in bus
* in ferry
* in passenger vehicle
* in subway
* in train
* in tram
* motorcycling
* running
* unknown
* walking

The structure of the file looks like this:
```
{
  "type": "FeatureCollection",
  "features": [
    {
      "id": "0",
      "type": "Feature",
      "properties": {
        "hex_id": "882a100883fffff",
        "cycling": 0,
        "flying": 0,
        "in bus": 0,
        "in ferry": 0,
        "in passenger vehicle": 0,
        "in subway": 1,
        "in train": 0,
        "in tram": 0,
        "motorcycling": 0,
        "running": 0,
        "unknown": 0,
        "walking": 1,
        "total_trips": 2
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [-73.9703347627024, 40.7944146266829],
            [-73.97672033423, 40.7933611073594],
            [-73.9786882604702, 40.7888994656285],
            [-73.974271526561, 40.7854916749318],
            [-73.9678869827332, 40.7865449744332],
            [-73.9659181452274, 40.7910062844233],
            [-73.9703347627024, 40.7944146266829]
          ]
        ]
      }
    }
}
```

Due to the private nature of this data, I have not commited it to this public repository. It can be [downloaded here](https://drive.google.com/file/d/1DrH67Acjp7O71FqZ8znE69IerXOS1nDW/view?usp=sharing). It has been shared only with Mario, but if anyone else from the class is intrested, just request access and I will be happy to share.


## Combining Data Sets

My proposal is to combine this data with either NYC subway data to understand why in certain areas I may be more likely to take a car than the train, for example. I also would like to match this data with my saved Google Locations data to see if there tend to be many trips surrounding these places.
```
+----------------------------------+
| 1. Create polygons for H3 bins   |
+----------------------------------+
                |
                v
+----------------------------------+
| 2. Count trip start data for     |
|    each polygon                  |
+----------------------------------+
                |
                v
+----------------------------------+
| 3. Spatial join with locations   |
|    of saved places               |
+----------------------------------+
                |
                v
+----------------------------------+
| 4. Create visualizations of      |
|    combined data                 |
+----------------------------------+
```