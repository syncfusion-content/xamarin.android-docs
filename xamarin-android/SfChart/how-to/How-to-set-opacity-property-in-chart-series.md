---
layout: post
title: How to set opacity of chart series in Xamarin.Android
description: This session describes how the Syncfusion Xamarin.Android SfChart can be set a opacity in chart series.
platform: Android
control: Chart
documentation: ug
---

# Set the opacity for chart series in Xamarin.Android

The [`Alpha`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Alpha) property can be used to set opacity of chart series.

The code sample demonstrated as follows.

{% highlight c# %}

SplineAreaSeries splineAreaSeries = new SplineAreaSeries();splineAreaSeries.Color = Color.Green;
splineAreaSeries.StrokeWidth = 2;
splineAreaSeries.StrokeColor = Color.Black;
splineAreaSeries.Alpha = 0.5f;

![opacity support in Xamarin.Android Chart](how-to/images/opacity.png)