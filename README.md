## Geometry Utility Functions in Javascript

## Synopsis
guf.js is a small collection of functions that calculate geometric properties of a mesh. The key feature it currently provides is normal calculation (face & vertex normals).

## Code Example
```js
var guf = require('guf');

var positions = [[x,y,z], [x,y,z], [x,y,z], [x,y,z], ... ];
var cells = [[i0,i1,i2], [i0,i1,i2], [i0,i1,i2], ... ];

// Vertex Normals (Left Image)
var vertexNormals = guf.vertexNormals( positions, cells ) );

// Face Normals (Right Image)
var facePositions = [];
var faceNormals = [];

for( var i = 0; i < cells.length; i++ ) {
  var a = positions[ cells[ i ][ 0 ] ];
  var b = positions[ cells[ i ][ 1 ] ];
  var c = positions[ cells[ i ][ 2 ] ];
  var n = guf.calculateNormal( a, b, c );  
  facePositions.push( a, b, c );
  faceNormals.push( n, n, n );
}
```

<p style="text-align: center;">
<img src="https://cloud.githubusercontent.com/assets/555207/14104304/5e17abee-f559-11e5-814d-00f1a8f1dad6.png" width="440">

<img src="https://cloud.githubusercontent.com/assets/555207/14104303/5dfd6d6a-f559-11e5-80c1-d49f50f75dd8.png" width="440">
</p>

## Motivation
This library is part of a larger project / series of libraries that aspires to bring computational and parametric design to the web. This library helps render meshes so you can see if your mesh's normals are oriented properly. This is useful in applications that enable higher level computational design, 3d printing, g-code generation, cnc milling tool path creation, laser cutting paths, robotic motion planning, and more.

## Build Requirements
node.js (4.4.0+) & npm

## Installation
You can add this library to your project by running:
```
npm install --save https://github.com/YCAMInterlab/guf.js.git
```

or via npm:
```
npm install --save guf
```

## Examples
See https://github.com/rezaali/webgl-sketches/tree/master/hull

## Contribution
Copyright 2015-2016 [Reza Ali](http://www.syedrezaali.com) co-developed by [YCAMInterLab](http://interlab.ycam.jp/en/) during the [Guest Research Project v.3](http://interlab.ycam.jp/en/projects/guestresearch/vol3)

## License
Apache-2.0
