---
layout: post
title: Chart Tooltip
description: How to enable and customize the tooltip in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Tooltip

Tooltip for data points, can be enabled by setting `TooltipEnabled` method as `true`.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.DataSource = Data;

columnSeries.TooltipEnabled = true;

chart.Series.Add(columnSeries);

{% endhighlight %}

![](tooltip_images/tooltip_img1.png)

## Customizing appearance

For customizing the tooltip appearance, you need to add an instance of `ChartTooltipBehavior` to the `Behaviors` collection method of `SfChart`. You can use the following methods available in the `ChartTooltipBehavior`.

* `StrokeColor` – used to change the label border color.
* `StrokeWidth` – used to change the label border width.
* `BackgroundColor` – used to change the label background color.
* `MarginBottom` – specifies the bottom margin for tooltip text.
* `MarginTop` – specifies the top margin for tooltip text.
* `MarginLeft` – specifies the left margin for tooltip text.
* `MarginRight` – specifies the right margin for tooltip text.
* `TextColor` – used to change the text color.
* `TextSize` – used to change label font size, family and weight.
* `LabelFormat` – used to provide numeric or date time format of the tooltip text.
* `Duration` – used to set the duration of the tooltip.
* `OffsetX` - used to move the label horizontally.
* `OffsetY` - used to move the label vertically.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.DataSource = Data;

columnSeries.TooltipEnabled = true;

ChartTooltipBehavior chartTooltipBehavior = new ChartTooltipBehavior();

chartTooltipBehavior.BackgroundColor = Color.Blue;

chartTooltipBehavior.StrokeColor = Color.Cyan;

chartTooltipBehavior.StrokeWidth = 3;

chartTooltipBehavior.TextSize = 15;

chartTooltipBehavior.TextColor = Color.White;

chartTooltipBehavior.Duration = 10;

chart.Behaviors.Add(chartTooltipBehavior);

chart.Series.Add(columnSeries);

{% endhighlight %}

![](tooltip_images/tooltip_img2.png)