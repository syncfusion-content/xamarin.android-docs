---
layout: post
title: Data Point Selection
description: How to select the data point in Android Chart
platform: Android
control: Chart
documentation: ug
---

# Data Point Selection
You can select a data point by tapping on it. To enable the selection feature, you can use [`DataPointSelectionEnabled`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~DataPointSelectionEnabled.html) property. 

{% highlight c# %} 
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.DataPointSelectionEnabled = true;
{% endhighlight %}

![](selection_images/selection_img1.png)

Following properties are used to configure the selection feature,

* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~SelectedDataPointIndex.html) – used to programmatically select a data point.
* [`SelectedDataPointColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~SelectedDataPointColor.html) – used to change the selected data point color.

{% highlight c# %} 
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.DataPointSelectionEnabled = true;
columnSeries.SelectedDataPointIndex = 2;
columnSeries.SelectedDataPointColor = Color.Red;

{% endhighlight %}

![](selection_images/selection_img2.png)


N> For Accumulation series like pie, doughnut, pyramid and funnel, when you select a data point, the corresponding legend item also will be selected.

## Event

**SelectionChanging**

The [`SelectionChanging`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~SelectionChanging_EV.html) event of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) is used to subscribe the selection changing listener and this is triggered before the data point is selected. You can restrict a data point from being selected, by cancelling this event, by using [`setCancel(boolean)`]() property of the listener argument. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedSeries.html) – used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedDataPointIndex.html) – used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the previous selected data point index.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionChangingEvent~Cancel.html) – used to set the value indicating whether the selection should be cancelled.

**SelectionChanged**

The [`SelectionChanged`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~SelectionChanged_EV.html) event of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) is used to subscribe the selection changed listener and this triggered after a data point is selected. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionChangingEvent.html) – used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the previous selected data point index.
* [`Selected Segment`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedSegment.html) - used to get the selected segment of the series.