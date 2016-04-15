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

You can add multiple series using `Series` property of `SfChart` class.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries1 = new ColumnSeries()
{
	DataSource = Data1
};
chart.Series.Add(columnSeries1);

ColumnSeries columnSeries2 = new ColumnSeries()
{
	DataSource = Data2
};
chart.Series.Add(columnSeries2);

ColumnSeries columnSeries3 = new ColumnSeries()
{
	DataSource = Data3
};
chart.Series.Add(columnSeries3);

{% endhighlight %}

![](chartseries_images/chartseries_img1.png)

## Combination Series

`SfChart` allows you to render the combination of different types of series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries()
{
	DataSource = Data1
};
chart.Series.Add(columnSeries);

LineSeries lineSeries = new LineSeries()
{
	DataSource = Data2
};

{% endhighlight %}

![](chartseries_images/chartseries_img2.png)

**Limitation of Combination Chart**

* Bar, StackingBar, and StackingBar100 cannot be combined with the other Cartesian type series.
* Cartesian type series cannot be combined with accumulation series (pie, doughnut, funnel, and pyramid).

When the combination of Cartesian and accumulation series types are added to the series collection, the series which are similar to the first series will be rendered and other series will be ignored. Following code snippet illustrates this.

{% highlight c# %} 

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
	DataSource = Data1
};
chart.Series.Add(lineSeries);

PieSeries pieSeries = new PieSeries()
{
	DataSource = Data2
};
chart.Series.Add(pieSeries);

{% endhighlight %}

![](chartseries_images/chartseries_img3.png)

## Grouping Stacked Series

You can group and stack the similar stacked series types using `GroupingLabel` property of stacked series. The stacked series which contains the same `GroupingLabel` will be stacked in a single group.

{% highlight c# %} 
[C#]

StackingColumnSeries stackingColumnSeries1 = new StackingColumnSeries();
stackingColumnSeries1.DataSource = Data1;
stackingColumnSeries1.GroupingLabel = "GroupOne";
stackingColumnSeries1.Label = "Google";
chart.Series.Add(stackingColumnSeries1);

StackingColumnSeries stackingColumnSeries2 = new StackingColumnSeries();
stackingColumnSeries2.DataSource = Data2;
stackingColumnSeries2.GroupingLabel = "GroupTwo";
stackingColumnSeries2.Label = "Bing";
chart.Series.Add(stackingColumnSeries2);

StackingColumnSeries stackingColumnSeries3 = new StackingColumnSeries();
stackingColumnSeries3.DataSource = Data3;
stackingColumnSeries3.GroupingLabel = "GroupOne";
stackingColumnSeries3.Label = "Yahoo";
chart.Series.Add(stackingColumnSeries3);

StackingColumnSeries stackingColumnSeries4 = new StackingColumnSeries();
stackingColumnSeries4.DataSource = Data4;
stackingColumnSeries4.GroupingLabel = "GroupTwo";
stackingColumnSeries4.Label = "Ask";
chart.Series.Add(stackingColumnSeries4);

{% endhighlight %}

![](chartseries_images/chartseries_img4.png)

##Vertical Chart

`SfChart` allows you to change the orientation of the rendered chart by setting `Transposed` property to true.

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries();

lineSeries.Transposed = true;

chart.Series.Add(lineSeries);

{% endhighlight %}

![](chartseries_images/chartseries_img5.png)