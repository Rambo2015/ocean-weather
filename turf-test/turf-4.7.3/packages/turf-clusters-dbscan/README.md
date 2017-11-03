# @turf/clusters-dbscan

# clustersDbscan

Takes a set of [points](http://geojson.org/geojson-spec.html#point) and partition them into clusters according to [https://en.wikipedia.org/wiki/DBSCAN](DBSCAN's) data clustering algorithm.

**Parameters**

-   `points` **[FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)&lt;[Point](http://geojson.org/geojson-spec.html#point)>** to be clustered
-   `maxDistance` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Maximum Distance between any point of the cluster to generate the clusters (kilometers only)
-   `units` **\[[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)]** in which `maxDistance` is expressed, can be degrees, radians, miles, or kilometers (optional, default `kilometers`)
-   `minPoints` **\[[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)]** Minimum number of points to generate a single cluster,
    points which do not meet this requirement will be classified as an 'edge' or 'noise'. (optional, default `3`)

**Examples**

```javascript
// create random points with random z-values in their properties
var points = turf.random('point', 100, {
  bbox: [0, 30, 20, 50]
});
var distance = 100;
var clustered = turf.clustersDbscan(points, distance);

//addToMap
var addToMap = [clustered];
```

Returns **[FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)&lt;[Point](http://geojson.org/geojson-spec.html#point)>** Clustered Points with an additional two properties associated to each Feature:-   {number} cluster - the associated clusterId
-   {string} dbscan - type of point it has been classified as ('core'|'edge'|'noise')

<!-- This file is automatically generated. Please don't edit it directly:
if you find an error, edit the source file (likely index.js), and re-run
./scripts/generate-readmes in the turf project. -->

---

This module is part of the [Turfjs project](http://turfjs.org/), an open source
module collection dedicated to geographic algorithms. It is maintained in the
[Turfjs/turf](https://github.com/Turfjs/turf) repository, where you can create
PRs and issues.

### Installation

Install this module individually:

```sh
$ npm install @turf/clusters-dbscan
```

Or install the Turf module that includes it as a function:

```sh
$ npm install @turf/turf
```