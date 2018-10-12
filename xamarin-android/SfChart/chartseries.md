---
layout: post
title:  Multiple chart series
description: Learn how to render different types of series in a chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Chart Series

## Multiple Series

You can add multiple series using [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html) property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) class. By default, all the series rendered based on the [`PrimaryAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~PrimaryAxis.html) and [`SecondaryAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~SecondaryAxis.html) of [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html). But if you want to plot different unit or value that is specific to particular series, you can specify the separate axis for that series using [`XAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~XAxis.html) and [`YAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~YAxis.html) properties of [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html).

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries1 = new ColumnSeries()
{
	ItemsSource = Data1,
    XBindingPath = "Country",
    YBindingPath = "Count"
};
chart.Series.Add(columnSeries1);

ColumnSeries columnSeries2 = new ColumnSeries()
{
	ItemsSource = Data2,
	XBindingPath = "Country",
    YBindingPath = "Count"
};
chart.Series.Add(columnSeries2);

ColumnSeries columnSeries3 = new ColumnSeries()
{
	ItemsSource = Data3,
	XBindingPath = "Country",
    YBindingPath = "Count"
};
chart.Series.Add(columnSeries3);

{% endhighlight %}

![Multiple series support in Xamarin.Android Chart](chartseries_images/chartseries_img1.png)

Following code snippet shows how to apply the Y axis to individual series to plot different values.

{% highlight c# %} 
[C#]

ColumnSeries series = new ColumnSeries();

series.ItemsSource = model.Demands;

series.XBindingPath = "XValue";

series.YBindingPath = "YValue";

series.Label = "Revenue";

chart.Series.Add(series);

LineSeries lineSeries = new LineSeries();

lineSeries.ItemsSource = model.Demands;

lineSeries.XBindingPath = "XValue";

lineSeries.YBindingPath = "YValue";

lineSeries.Label = "Customers";

NumericalAxis yAxis = new NumericalAxis();

yAxis.OpposedPosition = true;

yAxis.Title.Text = "Number of Customers";

lineSeries.YAxis = yAxis;

chart.Series.Add(lineSeries);

{% endhighlight %}

## Combination Series

[`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) allows you to render the combination of different types of series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries()
{
	ItemsSource = Data1,
	XBindingPath = "Month",
    YBindingPath = "Unit"
};
chart.Series.Add(columnSeries);

LineSeries lineSeries = new LineSeries()
{
	ItemsSource = Data2,
	XBindingPath = "Month",
    YBindingPath = "Unit"
};

{% endhighlight %}

![Combination of series support in Xamarin.Android Chart](chartseries_images/chartseries_img2.png)

**Limitation of Combination Chart**

* Bar, StackingBar, and StackingBar100 cannot be combined with the other Cartesian type series.
* Cartesian type series cannot be combined with accumulation series (pie, doughnut, funnel, and pyramid).

When the combination of Cartesian and accumulation series types are added to the series collection, the series which are similar to the first series will be rendered and other series will be ignored. Following code snippet illustrates this.

{% highlight c# %} 

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
	ItemsSource = Data1,
	XBindingPath = "Month",
    YBindingPath = "Unit"
};
chart.Series.Add(lineSeries);

PieSeries pieSeries = new PieSeries()
{
	ItemsSource = Data2,
	XBindingPath = "Month",
    YBindingPath = "Unit"
};
chart.Series.Add(pieSeries);

{% endhighlight %}

![Limitation of Xamarin.Android Chart series combination](chartseries_images/chartseries_img3.png)

## Grouping Stacked Series

You can group and stack the similar stacked series types using [`GroupingLabel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.StackingSeriesBase~GroupingLabel.html) property of stacked series. The stacked series which contains the same [`GroupingLabel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.StackingSeriesBase~GroupingLabel.html) will be stacked in a single group.

{% highlight c# %} 
[C#]

StackingColumnSeries stackingColumnSeries1 = new StackingColumnSeries();
stackingColumnSeries1.ItemsSource = Data1;
stackingColumnSeries1.XBindingPath = "Year";
stackingColumnSeries1.YBindingPath = "Visitors";
stackingColumnSeries1.GroupingLabel = "GroupOne";
stackingColumnSeries1.Label = "Google";
chart.Series.Add(stackingColumnSeries1);

StackingColumnSeries stackingColumnSeries2 = new StackingColumnSeries();
stackingColumnSeries2.ItemsSource = Data2;
stackingColumnSeries2.XBindingPath = "Year";
stackingColumnSeries2.YBindingPath = "Visitors";
stackingColumnSeries2.GroupingLabel = "GroupTwo";
stackingColumnSeries2.Label = "Bing";
chart.Series.Add(stackingColumnSeries2);

StackingColumnSeries stackingColumnSeries3 = new StackingColumnSeries();
stackingColumnSeries3.ItemsSource = Data3;
stackingColumnSeries3.XBindingPath = "Year";
stackingColumnSeries3.YBindingPath = "Visitors";
stackingColumnSeries3.GroupingLabel = "GroupOne";
stackingColumnSeries3.Label = "Yahoo";
chart.Series.Add(stackingColumnSeries3);

StackingColumnSeries stackingColumnSeries4 = new StackingColumnSeries();
stackingColumnSeries4.ItemsSource = Data4;
stackingColumnSeries4.XBindingPath = "Year";
stackingColumnSeries4.YBindingPath = "Visitors";
stackingColumnSeries4.GroupingLabel = "GroupTwo";
stackingColumnSeries4.Label = "Ask";
chart.Series.Add(stackingColumnSeries4);

{% endhighlight %}

![Grouping support for stacked series in Xamarin.Android Chart](chartseries_images/chartseries_img4.png)

## Animation

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) provides animation support for data series. Series will be animated whenever the ItemsSource changes. Animation can be enabled by using the [`EnableAnimation`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~EnableAnimation.html) property. You can also control the duration of the animation using [`AnimationDuration`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~AnimationDuration.html) property. 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.ItemsSource = dataPoints;

columnSeries.XBindingPath = "XValue";

columnSeries.YBindingPath = "YValue";

columnSeries.EnableAnimation = true;

columnSeries.AnimationDuration = 2;

{% endhighlight %}

## Transpose the Series (Vertical Chart)


The [`Transposed`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~Transposed.html) property of [`CartesianSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~Transposed.html) is used to plot the chart vertically and view the data in a different perspective.

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries();

lineSeries.Transposed = true;

chart.Series.Add(lineSeries);

{% endhighlight %}

![Series transpose support in Xamarin.Android Chart](chartseries_images/chartseries_img5.png)

## Methods

The following methods are available in [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html)

* [`FindNearestChartPoint(float pointX,float pointY)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~FindNearestChartPoint.html) - Gets the nearest data point for a particular touch point. 
* [`FindNearestChartPoints(float pointX,float pointY)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~FindNearestChartPoints.html) - Gets the list of nearest data points for a particular touch point.
* [`CreateSegment()`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~CreateSegment.html) and [`CreateSegments()`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~CreateSegments.html) - Overriding these methods, we can customize the rendering of segments.

## Adding separate view for series

The SeriesRender view is used to render [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html) using the GetView method. The following code sample demonstrates how to add separate view for series. 

{% highlight c# %}
[C#]

public class CustomColumnSeries : ColumnSeries
    {
        protected override SeriesRenderer GetView()
        {
            var view = new SeriesRenderer(Android.App.Application.Context);
            return view;
        }
    }

{% endhighlight %}