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
fastLineSeries.YBindingPath = "YValue;

chart.Series.Add(fastLineSeries);

{% endhighlight %}

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** to view the point information.

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.

N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.

## Add range of points dynamically

Whenever you add a data point to the ItemsSource dynamically, the corresponding data will be updated inside the chart series synchronously. This operation will be happening for each data point that you add subsequently. You can avoid this by calling the [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~SuspendSeriesNotification.html) method of chart before adding the range of data points and calling the [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~ResumeSeriesNotification.html) to update all the data points that have been added between these two method calls.

{% highlight c# %}

 	Chart.SuspendSeriesNotification();

		// ...

		// Add multiple data points.

		// ...

	Chart.ResumeSeriesNotification();

{% endhighlight %}

As similarly, you can use [`SuspendNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~SuspendNotification.html) and [`ResumeNotification`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~ResumeNotification.html) methods in the chart series to update the all the data points that have been added between these two method calls.

{% highlight c# %}

 	series.SuspendNotification();

		// ...

		// Add multiple data points.

		// ...

	series.ResumeNotification();

{% endhighlight %}

