---
layout: post
title: Data Point Selection in Syncfusion Chart
description: How to select the data point in Android Chart
platform: Android
control: Chart
documentation: ug
---

# Selection

[`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) supports selection that enables you to select a segment in a series or series itself.

## Data Point Selection
You can select a data point by tapping on it. To enable the selection feature, you can use [`DataPointSelectionEnabled`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~DataPointSelectionEnabled.html) property. 

{% highlight c# %} 
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.DataPointSelectionEnabled = true;
{% endhighlight %}

![Data point selection support in Xamarin.Android Chart](selection_images/selection_img1.png)

Following properties are used to configure the selection feature,

* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~SelectedDataPointIndex.html) – used to programmatically select a data point.
* [`SelectedDataPointColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~SelectedDataPointColor.html) – used to change the selected data point color.

{% highlight c# %} 
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.DataPointSelectionEnabled = true;
columnSeries.SelectedDataPointIndex = 2;
columnSeries.SelectedDataPointColor = Color.Red;

{% endhighlight %}

![Selecting data point and data point color support in Xamarin.Android Chart](selection_images/selection_img2.png)


N> For Accumulation series like pie, doughnut, pyramid and funnel, when you select a data point, the corresponding legend item also will be selected.

## Series Selection

Series selection is used in case of multiple series when you want to highlight a particular series. Series Selection can be enabled by setting [`EnableSeriesSelection`]() property to true. The [`SeriesSelectionColor`]() property is used to set the color to highlight the series.

{% highlight c# %} 
[C#]

chart.EnableSeriesSelection = true;
chart.SeriesSelectionColor = Color.Rgb(0, 155, 247);

...

ColumnSeries series = new ColumnSeries();
series.ItemsSource = viewModel.Data;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
series.Color = Color.Rgb(178,225,253);
chart.Series.Add(series);

ColumnSeries series1 = new ColumnSeries();
series1.ItemsSource = viewModel.Data1;
series1.XBindingPath = "XValue";
series1.YBindingPath = "YValue";
series1.Color = Color.Rgb(178, 225, 253);
chart.Series.Add(series1);

{% endhighlight %}

![Series selection support in Xamarin.Android Chart](selection_images/seriesSelection.png)

## Event

**SelectionChanging**

The [`SelectionChanging`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~SelectionChanging_EV.html) event of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) is used to subscribe the selection changing event and this is triggered before the data point is selected. You can restrict a data point from being selected, by canceling this event, by using [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionChangingEvent~Cancel.html) property of the event argument. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedSeries.html) – used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedDataPointIndex.html) – used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the previous selected data point index.
* [`PreviousSelectedSeries`]() - used to get the previous selected series. 
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionChangingEvent~Cancel.html) – used to set the value indicating whether the selection should be canceled.

**SelectionChanged**

The [`SelectionChanged`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~SelectionChanged_EV.html) event of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) is used to subscribe the selection changed event and this triggered after a data point is selected. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedSeries.html) – used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~PreviousSelectedIndex.html) – used to get the previous selected data point index.
* [`PreviousSelectedSeries`]() - used to get the previous selected series.
* [`SelectedSegment`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSelectionEvent~SelectedSegment.html) - used to get the selected segment of the series.