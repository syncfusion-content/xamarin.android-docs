---
layout: post
title: Populating data
description: How to add data point to series in  Essential Xamarin.Android Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Populating Data

SfChart control can be configured with data points using [`DataSource`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~DataSource.html) property of [`ChartSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html). You can create a collection of [`ChartDataPoint`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartDataPoint.html) objects and set this collection using DataSource property. Here, each ChartDataPoint object represents a data point in a chart series.

N> [`ChartDataPoint`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartDataPoint.html) class has few overloaded constructors depending on the number of y-values required to plot a data point for a particular series type. For example, you can use a constructor with two parameters to instantiate data point for XYDataSeries like Line, Spline, and Pie etc.

Following code snippet illustrates this,

{% highlight c# %}
[C#]  

ObservableArrayList highTemperature = new ObservableArrayList();

highTemperature.Add(new ChartDataPoint("Jan", 42));
highTemperature.Add(new ChartDataPoint("Feb", 44));
highTemperature.Add(new ChartDataPoint("Mar", 53));
highTemperature.Add(new ChartDataPoint("Apr", 64));
highTemperature.Add(new ChartDataPoint("May", 75));
highTemperature.Add(new ChartDataPoint("Jun", 83));
highTemperature.Add(new ChartDataPoint("Jul", 87));
highTemperature.Add(new ChartDataPoint("Aug", 84));
highTemperature.Add(new ChartDataPoint("Sep", 78));
highTemperature.Add(new ChartDataPoint("Oct", 67));
highTemperature.Add(new ChartDataPoint("Nov", 55));
highTemperature.Add(new ChartDataPoint("Dec", 45));

{% endhighlight %}
