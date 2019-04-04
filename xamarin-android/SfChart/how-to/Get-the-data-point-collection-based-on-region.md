---
layout: post
title: Get the data point collection based on region in Syncfusion SfChart
description: Get the data point collection based on region in SfChart
platform: Android
control: Chart
documentation: ug
---

# Get the data point collection based on region

[`CartesianSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries.html) provides the following methods to get the visible range data points: 

* [`GetDataPoints(RectangleF rect)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~GetDataPoints(RectangleF).html) - Gets the collection of data that fall inside the given rectangle region.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~GetDataPoints(Double,Double,Double,Double).html) - Gets the collection of data from the given ChartAxis visible range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

or

List<object> dataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}

N> You can get the visible plotting region of the series in the chart using [`SeriesClipRect`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~SeriesClipRect.html) or [`SeriesBounds`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~SeriesBounds.html) property in run time.