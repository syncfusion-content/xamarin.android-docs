---
layout: post
title: Chart Tooltip
description: How to enable and customize the tooltip in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Tooltip

Tooltip for data points, can be enabled by setting [`TooltipEnabled`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~TooltipEnabled.html) property as `true`.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.ItemsSource = Data;

columnSeries.XBindingPath = "XValue";

columnSeries.YBindingPath = "YValue";

columnSeries.TooltipEnabled = true;

chart.Series.Add(columnSeries);

{% endhighlight %}

![Tooltip support in Xamarin.Android Chart](tooltip_images/tooltip_img1.png)

## Customizing appearance

For customizing the tooltip appearance, you need to add an instance of [`ChartTooltipBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior.html) to the [`Behaviors`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBehavior.html) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html). You can use the following properties available in the [`ChartTooltipBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior.html).

* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~StrokeColor.html) – used to change the label border color.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~StrokeWidth.html) – used to change the label border width.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~BackgroundColor.html) – used to change the label background color.
* [`MarginBottom`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~MarginBottom.html) – specifies the bottom margin for tooltip text.
* [`MarginTop`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~MarginTop.html) – specifies the top margin for tooltip text.
* [`MarginLeft`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~MarginLeft.html) – specifies the left margin for tooltip text.
* [`MarginRight`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~MarginRight.html) – specifies the right margin for tooltip text.
* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~TextColor.html) – used to change the text color.
* [`TextSize`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~TextSize.html) – used to change label font size, family and weight.
* [`LabelFormat`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~LabelFormat.html) – used to provide numeric or date time format of the tooltip text.
* [`Duration`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~Duration.html) – used to set the duration of the tooltip.
* [`OffsetX`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~OffsetX.html) - used to move the label horizontally.
* [`OffsetY`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~OffsetY.html) - used to move the label vertically.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.ItemsSource = Data;

columnSeries.XBindingPath = "XValue";

columnSeries.YBindingPath = "YValue";

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

![Customizing the appearance of tooltip in Xamarin.Android Chart](tooltip_images/tooltip_img2.png)

## Customizing the appearance of tooltip view 

The following properties are available to customize the appearance of tooltip view. We can achieve this by overriding the GetView method of [`ChartTooltipBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior.html). 

* [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TooltipView~Series.html) - returns the series at the tapped location.
* [`XPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TooltipView~XPosition.html) - returns the x position of the tooltip.
* [`YPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TooltipView~YPosition.html) - returns the y position of the tooltip.
* [`LabelRect`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TooltipView~LabelRect.html) - returns the tooltip label rect.
* [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TooltipView~CornerRadius.html) - used to change the corner radius of the tooltip. 

## Methods

You can show or hide the chart tooltip programmatically by using the show or hide method. 

### Show method

The  [`Show`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~Show.html) method is used to activate the tooltip at the specified location.

{% highlight c# %}


//Arguments are x position, y position and bool value determines whether the tooltip should be animated while displaying.
	
tooltip.Show(pointX, pointY, true);

{% endhighlight %}


N>The tooltip will be activated at the specified location only if there is any data point under the specified location.

## Hide method

The  [`Hide`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTooltipBehavior~Hide.html)  method is used to hide the tooltip programmatically.

{% highlight c# %}

//The argument determines whether the tooltip should be animated while hiding.

tooltip.Hide(true);

{% endhighlight %}
