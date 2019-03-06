---
layout: post
title: Transform axis value to pixel value and vice-versa | Syncfusion
description: Transform axis value to pixel value and vice-versa in SfChart
platform: Android
control: Chart
documentation: ug
---

## Transform axis value to pixel value and vice-versa

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) offers two utility methods to transform the pixel to chart point and vice-versa.

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~ValueToPoint.html) - Converts the data point value to screen point.
* [`PointToValue(ChartAxis axis, PointF point)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~PointToValue(ChartAxis,PointF).html) - Converts the screen point to chart value.

{% highlight c# %}

double xValue = Chart.PointToValue(Chart.PrimaryAxis, screenPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, screenPoint);

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

Use the [`ValueToPoint`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~ValueToPoint.html) and [`PointToValue`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~PointToValue(PointF).html) methods, which are available in [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis.html), to convert the screen point within the rendered area of the series.

N> You can convert the actual axis value to 0 to 1 coefficient using the [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~ValueToCoefficient.html) and [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~CoefficientToValue.html) methods of [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis.html).
