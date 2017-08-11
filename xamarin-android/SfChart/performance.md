---
layout: post
title: Performance tips
description: How to improve the performance of Essential Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Performance

When there are large number of points to load in line series, you can use [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FastLineSeries.html) series instead of [`LineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.LineSeries.html). To renderer a fast line chart, create an instance of [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FastLineSeries.html) and add to the series using [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html) property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html).

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries();
fastLineSeries.ItemsSource = Data;
fastLineSeries.XBindingPath = "XValue";
fastLineSeries.YBindigPath = "YValue;

chart.Series.Add(fastLineSeries);

{% endhighlight %}

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** to view the point information.