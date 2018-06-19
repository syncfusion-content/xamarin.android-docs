---
layout: post
title:  Legends of Essential Xamarin.Android SfSunburstChart
description: This section describes the legend and its customization.
platform: Xamarin.Android
control: SfSunburstChart
documentation: ug
---

# Legend

Legends are used to represent the first level (i.e root level) of categories in the sunburst chart.

## Visibility

The visibility of legends can be controlled using the [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~IsVisible.html) property.

The following code shows how to control the visibility of legend.

{% tabs %} 

{% highlight C# %} 

sunburstChart.Legend.IsVisible = true;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/Legend.jpg)


## Position

Legends can be docked at the top, right, left, or bottom position using the [`LegendPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~LegendPosition.html) property.

The following code shows customizing the legend position.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.Legend.IsVisible = true;
            sunburstChart.Legend.LegendPosition = SunburstDockPosition.Left;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/LegendPosition.jpg)


## Legend icon types

Legend icon shapes can be customized using the [`IconType`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~IconType.html) property. The IconType property provides several predefined shapes. The default legend icon type is circle.

The following predefined shapes are available in the IconType property:
* Circle
* Cross
* Diamond
* Pentagon
* Rectangle
* Triangle.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.Legend.IsVisible = true;
            sunburstChart.Legend.IconType = SunburstLegendIcon.Diamond;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/IconType.jpg)

## Icon size customization

The size of the legend icon can be customized using the [`IconHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~IconHeight.html) and [`IconWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~IconWidth.html) properties.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.Legend.IsVisible = true;
            sunburstChart.Legend.IconType = SunburstLegendIcon.Diamond;
            sunburstChart.Legend.IconWidth = 15;
            sunburstChart.Legend.IconHeight = 15;            

{% endhighlight %}

{% endtabs %} 

![](Legend_images/IconSize.jpg)

## Label style

Legend label can be customized using the following properties available in [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~LabelStyle.html):

* [`Margin`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegendLabelStyle~Margin.html): Sets the specified margin for legend labels.
* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegendLabelStyle~Color.html): Customizes the text color of the label.
* [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegendLabelStyle~TextSize.html): Customizes the label's text size.
* [`Typeface`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegendLabelStyle~Typeface.html): Typeface of the labels can be customized.


{% tabs %} 

{% highlight C# %} 

            sunburstChart.Legend.IsVisible = true;
            sunburstChart.Legend.LabelStyle.Color = Color.Red;
            sunburstChart.Legend.LabelStyle.Margin = new Thickness(5);
            sunburstChart.Legend.LabelStyle.TextSize = 14;
            sunburstChart.Legend.LabelStyle.Typeface = Typeface.Serif;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/LabelStyle.png)


## Item margin

Margin can be set to individual legend items using the [`ItemMargin`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfsunburstchart/Syncfusion.SfSunburstChart.Android~Syncfusion.SfSunburstChart.Android.SunburstChartLegend~ItemMargin.html) property.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.Legend.IsVisible = true;
            sunburstChart.Legend.ItemMargin = new Thickness(3, 3, 3, 3);           

{% endhighlight %}

{% endtabs %} 

![](Legend_images/ItemMargin.png)

