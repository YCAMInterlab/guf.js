## Geometry Utility Functions in Javascript

## Synopsis
guf.jsは、メッシュの幾何学的特性を算出する、簡単な関数コレクションです。現在備えている主要機能は、面や頂点の法線計算です。

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
このライブラリは、コンピュテーショナル デザイン、及びパラメトリック デザインをウェブに広めようとする、大きなライブラリのプロジェクト/シリーズの一部です。
高度なコンピューテーショナル デザインや3Dモデルの出力、Gコード生成、CNCフライス加工ツール用のパスや、レーザー切断用のパスの生成、ロボット運動計画などを可能にする、全ての複雑な形態機能を備えた数学的頭脳になることを目的としています。

## Build Requirements
node.js (4.4.0+) & npm

## Installation
このライブラリをプロジェクトに追加するためには、以下の操作を行って下さい:
```
npm install --save https://github.com/YCAMInterlab/guf.js.git
```

もしく以下の方法でも追加できます:
```
npm install --save guf
```

## Examples
See https://github.com/rezaali/webgl-sketches/tree/master/hull

## Contribution
Copyright 2015-2016 [Reza Ali](http://www.syedrezaali.com) co-developed by [YCAMInterLab](http://interlab.ycam.jp/en/) during the [Guest Research Project v.3](http://interlab.ycam.jp/en/projects/guestresearch/vol3)

## License
Apache-2.0
