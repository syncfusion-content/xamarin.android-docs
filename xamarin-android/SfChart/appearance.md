---
layout: post
title: Customizing the appearance of Essential Xamarin.Android Chart
description: Learn how to customize the appearance of Chart using palettes.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Color Palette

## Apply palette for Series

`ColorModel` property of `SfChart` is used to define the colors for each series. ColorModel contains the following color palettes.

**Predefined Palettes**

Currently, Chart supports only Metro palette and it is the default palette for SfChart. The following screenshot shows the default appearance of multiple series.

![](appearance_images/appearance_img1.png)

**Custom Palette**

You can apply the custom colors by setting the palette as `Custom` using `ColorPalette` and provide the custom colors using `CustomColors` property.

Following code illustrates how to set the custom colors.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart(this);
...

var colors = new List<Integer>();
colors.Add(new Integer(Color.ParseColor("#FFEAE018")));
colors.Add(new Integer(Color.ParseColor("#FFB3B1AD")));
colors.Add(new Integer(Color.ParseColor("#FF8C0707")));

chart.ColorModel.ColorPalette = ChartColorPalette.Custom;
chart.ColorModel.CustomColors = colors;

{% endhighlight %}

![](appearance_images/appearance_img2.png)

**None Palette**

None palette will not apply any color to the series. So in order to define the color for any series, you can use the `Color` property or the `ColorModel` property of ChartSeries (The ColorModel of Series will be explained later in this document).

## Apply palette for data points

`ColorModel` property of ChartSeries is used to define the colors for each data point. Following palettes are used to define the colors.

**Predefined Palettes**

Currently, Chart supports only Metro palette.

{% highlight c# %} 
[C#]

ColumnSeries columnSeies = new ColumnSeries();
columnSeies.ColorModel.ColorPalette = ChartColorPalette.Metro;

{% endhighlight %}

![](appearance_images/appearance_img3.png)

**Custom Palette**

You can apply the custom colors by setting the palette as `Custom` using `ColorPalette` and provide the custom colors using `setCustomColors` property.

Following code illustrates how to set the custom colors.

{% highlight c# %} 
[C#]

var colors = new List<Integer>();
colors.Add(new Integer(Color.Red));
colors.Add(new Integer(Color.Gray));
colors.Add(new Integer(Color.Blue));
colors.Add(new Integer(Color.Maroon));
colors.Add(new Integer(Color.Pink));

ColumnSeries columnSeies = new ColumnSeries();
columnSeies.ColorModel.ColorPalette = ChartColorPalette.Custom;
columnSeies.ColorModel.CustomColors = colors;

{% endhighlight %}

![](appearance_images/appearance_img4.png)

**None Palette**

None palette will not apply any color to the data points. So in order to define the color for the data points, you can use the `Color` property of ChartSeries.