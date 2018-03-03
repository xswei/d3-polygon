# d3-polygon

这个模块提供了基础的二维多边形几个基本的操作。每个多边形被描述为一个二维数组的数组: [​[<i>x1</i>, <i>y1</i>], [<i>x2</i>, <i>y2</i>], …], 可以是闭合的(第一个点坐标等于最后一个点坐标)也可以是开放的(第一个点坐标不等于最后一个点坐标)。典型的多边形各个定点安装逆时针顺序连接，坐标系统的左上角为 ⟨0,0⟩ 点。

## Installing

NPM：`npm install d3-polygon`。也可以下载 [latest release](https://github.com/d3/d3-polygon/releases/latest). 可以直接从 [d3js.org](https://d3js.org) 以 [standalone library](https://d3js.org/d3-polygon.v1.min.js) 或  [D3 4.0](https://github.com/d3/d3) 一部分的形式直接载入. 支持 AMD, CommonJS 以及最基本的标签引入形式. 通过标签引入会暴露一个 `d3` 全局变量:

```html
<script src="https://d3js.org/d3-polygon.v1.min.js"></script>
<script>

var hull = d3.polygonHull(points);

</script>
```

[在浏览器中测试 d3-polygon ](https://tonicdev.com/npm/d3-polygon)

## API Reference

<a href="#polygonArea" name="polygonArea">#</a> d3.<b>polygonArea</b>(<i>polygon</i>) [<>](https://github.com/d3/d3-polygon/blob/master/src/area.js#L1 "Source Code")

返回指定 *polygon* 的面积。如果多边形的定点是逆时针连接(假设坐标系统 ⟨0,0⟩ 点位于左上角)则返回值为正，否则为负或 0.

<a href="#polygonCentroid" name="polygonCentroid">#</a> d3.<b>polygonCentroid</b>(<i>polygon</i>) [<>](https://github.com/d3/d3-polygon/blob/master/src/centroid.js#L1 "Source Code")

返回指定 *polygon* 的[centroid(几何中心)](https://en.wikipedia.org/wiki/Centroid)。

<a href="#polygonHull" name="polygonHull">#</a> d3.<b>polygonHull</b>(<i>points</i>) [<>](https://github.com/d3/d3-polygon/blob/master/src/hull.js#L23 "Source Code")

<a href="http://bl.ocks.org/mbostock/6f14f7b7f267a85f7cdc"><img src="https://raw.githubusercontent.com/d3/d3-polygon/master/img/hull.png" width="250" height="250"></a>

使用 [Andrew’s monotone chain algorithm(二维凸包算法)](http://en.wikibooks.org/wiki/Algorithm_Implementation/Geometry/Convex_hull/Monotone_chain) 计算指定的一系列点的 [convex hull(凸包)](https://en.wikipedia.org/wiki/Convex_hull)。返回的凸包由一组输入点的子集表示，并且顺序为逆时针。如果输入的 *points* 个数小于 3 则返回 null。

<a href="#polygonContains" name="polygonContains">#</a> d3.<b>polygonContains</b>(<i>polygon</i>, <i>point</i>) [<>](https://github.com/d3/d3-polygon/blob/master/src/contains.js#L1 "Source Code")

当且仅当指定的 *point* [inside the specified *polygon*(在指定的多边形内部)](https://www.ecse.rpi.edu/Homepages/wrf/Research/Short_Notes/pnpoly.html) 则返回 true。

<a href="#polygonLength" name="polygonLength">#</a> d3.<b>polygonLength</b>(<i>polygon</i>) [<>](https://github.com/d3/d3-polygon/blob/master/src/length.js#L1 "Source Code")

返回指定 *polygon* 的周长.
