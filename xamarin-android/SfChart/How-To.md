---
layout: post
title: Customizations in SfChart
description: Customizations in SfChart
platform: Android
control: Chart
documentation: ug
---

# How to

##  Get a data point collection based on region

[`CartesianSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries.html) provides the following methods to get the visible range data points.

* [`GetDataPoints(RectangleF rect)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~GetDataPoints(RectangleF).html) - Gets a collection of data that fall inside the given rectangle region.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~GetDataPoints(Double,Double,Double,Double).html) - Gets a collection of data from the given ChartAxis visible range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

or

List<object> dataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}