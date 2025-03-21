---
layout: post
title: Shape type in Syncfusion<sup>&reg;</sup> SfMaps control for Xamarin.Forms
description: This section describes the shape type of shape file layer on maps control.
platform: Xamarin.Android
control: SfMaps
documentation: ug
---

# Shape Type

[`SfMaps`](https://help.syncfusion.com/xamarin-android/sfmaps/getting-started) allows to provide various shape types in [`ShapeFileLayer`](https://help.syncfusion.com/xamarin-android/sfmaps/layers#shape-file-layer) such as Polygon, Polyline, and Points.

## Polygon

Polygon is a two-dimensional surface stored as a sequence of points defining its exterior bounding ring and 0 or more interior rings. Polygons are always simple. Mostly the polygon shape type defines a group of land, water bodies, and other features that have a spatial extent.

![Single selection support in Xamarin.Forms Maps](Images/polygon.jpg)

## Polyline

The polyline is a shape that has a dimension of 1. It is called a simple line if it does not intersect itself. The polylines are often used to define linear features such as roads, rivers, and power lines. Mostly the shape file layer with the polyline shape type is used as [`sublayer`](https://help.syncfusion.com/xamarin-android/sfmaps/sublayer#adding-sublayer).

The following code example demonstrates the sublayer with polyline shape type. The roads (sublayer) of Bahrain (base layer) is displayed using the shape file layer of maps.

{% tabs %}

{% highlight c# %}

SfMaps maps = new SfMaps(this);

ShapeFileLayer layer = new ShapeFileLayer();
 
 layer.Uri = "Bahrain.shp";

ShapeSetting layerSetting = new ShapeSetting();

layerSetting.ShapeFill = Color.ParseColor("#bcbcbc");

layer.ShapeSettings = layerSetting;

SubShapeFileLayer subLayer = new SubShapeFileLayer();

subLayer.Uri = "roads.shp";

ShapeSetting subLayerSetting = new ShapeSetting();
            
subLayerSetting.ShapeFill = Color.Black;
            
subLayerSetting.ShapeStrokeThickess = 2;

subLayer.ShapeSettings = subLayerSetting;

layer.SubShapeFileLayers.Add(subLayer);

maps.Layers.Add(layer);

SetContentView(maps);


{% endhighlight %}

{% endtabs %}

![Single selection support in Xamarin.Forms Maps](Images/polyline.jpg)

## Points

A point is shape with a dimension of 0 that occupies a single location in coordinate space. A point has a single x, y coordinate value. The points are often used to define features such as oil wells, landmarks, and elevations.

The following code example demonstrates the [`sublayer`](https://help.syncfusion.com/xamarin-android/sfmaps/sublayer#adding-sublayer) with the points shape type. The places (sublayer) of Australia (base layer) is displayed using the shape file layer of maps.

{% tabs %}

{% highlight c# %}

SfMaps maps = new SfMaps();

ShapeFileLayer layer = new ShapeFileLayer();

layer.Uri = "australia.shp";

ShapeSetting layerSetting = new ShapeSetting();

layerSetting.ShapeFill = Color.FromHex("#bcbcbc");

layer.ShapeSettings = layerSetting;

ShapeFileLayer subLayer = new ShapeFileLayer();

subLayer.Uri = "points.shp";

subLayer.MapPointIconSize = 5;

ShapeSetting subLayerSetting = new ShapeSetting();

subLayerSetting.ShapeFill = Color.Black;

subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);

maps.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/points.jpg)

### Customization of Points

The size, shape, and position of the map points can be customized using the [`MapPointIconSize`], [`MapPointIcon`], [`MapPointHorizontalAlignment`] and [`MapPointVerticalAlignment`]  properties of shape file layer.

### Map point icon

The shape of the map point is customized using the [`MapPointIcon`] property of ShapeFileLayer. SfMap supports the following map point icon types: 

*	Circle,
*	Rectangle,
*	Square,
*	Diamond,
*	Star

{% tabs %}

{% highlight c# %}

SfMaps maps = new SfMaps(this);

ShapeFileLayer layer = new ShapeFileLayer();

layer.Uri = "australia.shp";

ShapeSetting layerSetting = new ShapeSetting();

layerSetting.ShapeFill = Color.ParseColor("#bcbcbc");

layer.ShapeSettings = layerSetting;

SubShapeFileLayer subLayer = new SubShapeFileLayer();
            
subLayer.Uri = "points.shp";

subLayer.MapPointIcon = MapPointIcon.Circle;

subLayer.MapPointIconSize = 15;

ShapeSetting subLayerSetting = new ShapeSetting();

subLayerSetting.ShapeFill = Color.Green;

subLayer.ShapeSettings = subLayerSetting;

layer.SubShapeFileLayers.Add(subLayer);

maps.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/icons.png)

### Map point position

The position of the map points can be customized using the [`MapPointHorizontalAlignment`] and [`MapPointVerticalAlignment`] properties of shape file layer. These properties allow to vary the position to Near, Far, and Center by considering the provided latitude, longitude, and the map point icon size.

{% tabs %}

{% highlight c# %}

SfMaps maps = new SfMaps(this);

ShapeFileLayer layer = new ShapeFileLayer();
            
layer.Uri = "australia.shp";

ShapeSetting layerSetting = new ShapeSetting();
            
layerSetting.ShapeFill = Color.ParseColor("#bcbcbc");
            
layer.ShapeSettings = layerSetting;

SubShapeFileLayer subLayer = new SubShapeFileLayer();
            
subLayer.Uri = "points.shp";
            
subLayer.MapPointIcon = MapPointIcon.Circle;
            
subLayer.MapPointIconSize = 15;
            
subLayer.MapPointHorizontalAlignment = MarkerAlignment.Near;
            
subLayer.MapPointHorizontalAlignment = MarkerAlignment.Near;
            
ShapeSetting subLayerSetting = new ShapeSetting();
            
subLayerSetting.ShapeFill = Color.Brown;
            
subLayer.ShapeSettings = subLayerSetting;

layer.SubShapeFileLayers.Add(subLayer);
            
maps.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/mapAlignmnet.png)

### Map point size

The size of the map points can be customized using the [`MapPointIconSize`] property of  ShapeFileLayer.

{% tabs %}

{% highlight c# %}

SfMaps maps = new SfMaps(this);

ShapeFileLayer layer = new ShapeFileLayer();
            
layer.Uri = "australia.shp";

ShapeSetting layerSetting = new ShapeSetting();
            
layerSetting.ShapeFill = Color.ParseColor("#bcbcbc");
            
layer.ShapeSettings = layerSetting;

SubShapeFileLayer subLayer = new SubShapeFileLayer();
            
subLayer.Uri = "points.shp";
            
subLayer.MapPointIcon = MapPointIcon.Circle;
            
subLayer.MapPointIconSize = 15;
            
ShapeSetting subLayerSetting = new ShapeSetting();
            
subLayerSetting.ShapeFill = Color.OrangeRed;
            
subLayer.ShapeSettings = subLayerSetting;

layer.SubShapeFileLayers.Add(subLayer);
            
maps.Layers.Add(layer);

SetContentView(maps);

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/size.jpg)

