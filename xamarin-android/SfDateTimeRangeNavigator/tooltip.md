---
layout: post
title: Tooltip customization for DateTimeRangeNavigator
description: Tooltip customization
platform: Xamarin.Android
control: SfDateTimeRangeNavigator
documentation: ug
---

# Tooltip

The tooltip is used to show the selected range start and end value of the `SfDateTimeRangeNavigator``.`

## Tooltip Visibility

The [`TooltipEnabled`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~TooltipEnabled.html) property of `SfDateTimeRangeNavigator` is used to control the visibility of the left and right tooltip. It is true by default.

{% highlight c# %}
[C#]
SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator(this);

rangeNavigator.TooltipEnabled = false;
{% endhighlight %}

![](tooltip_images/tooltip_img1.png)

## Tooltip Format

You can format the date value of the tooltip using [`TooltipFormat`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~TooltipFormat.html) property of `SfDateTimeRangeNavigator`.

{% highlight c# %}
[C#]
dateTimeRangeNavigator.TooltipFormat = "yyyy/MM";
{% endhighlight %}

![](tooltip_images/tooltip_img2.png)

## Appearance Customization

The [`LeftTooltipStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~LeftTooltipStyle.html) and [`RightTooltipStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~RightTooltipStyle.html) properties of `SfDateTimeRangeNavigator` are used to customize the left and right tooltip. Following properties are available in each tooltip style to customize the appearance of the tooltip.

* [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~TextColor.html) – used to change the color of the tooltip text.
* [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~TextSize.html) - used to change the text size of the tooltip.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~BackgroundColor.html) – used to change the background color of the tooltip.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~StrokeColor.html) – used to change the border color of the tooltip.
* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~StrokeWidth.html) – used to change the thickness of the tooltip border.
* [`Typeface`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~Typeface.html) – used to change the font family and font weight
* [`MarginLeft`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~MarginLeft.html) - used to change the left margin of the tooltip text.
* [`MarginTop`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~MarginTop.html) - used to change the top margin of the tooltip text.
* [`MarginRight`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~MarginRight.html) - used to change the right margin of the tooltip text.
* [`MarginBottom`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.TooltipStyle~MarginBottom.html) - used to change the bottom margin of the tooltip text.

{% highlight c# %}
[C#]
dateTimeRangeNavigator.LeftTooltipStyle.TextColor = Color.Blue;
dateTimeRangeNavigator.LeftTooltipStyle.BackgroundColor = Color.White;
dateTimeRangeNavigator.LeftTooltipStyle.StrokeColor = Color.Blue;
dateTimeRangeNavigator.LeftTooltipStyle.StrokeWidth = 2;
dateTimeRangeNavigator.LeftTooltipStyle.TextSize = 30;
dateTimeRangeNavigator.LeftTooltipStyle.MarginLeft = 15;
dateTimeRangeNavigator.LeftTooltipStyle.MarginTop = 15;
dateTimeRangeNavigator.LeftTooltipStyle.MarginRight = 15;
dateTimeRangeNavigator.LeftTooltipStyle.MarginBottom = 15;
dateTimeRangeNavigator.RightTooltipStyle.TextColor = Color.Blue;
dateTimeRangeNavigator.RightTooltipStyle.BackgroundColor = Color.White;
dateTimeRangeNavigator.RightTooltipStyle.StrokeColor = Color.Blue;
dateTimeRangeNavigator.RightTooltipStyle.StrokeWidth = 2;
dateTimeRangeNavigator.RightTooltipStyle.TextSize = 30;
dateTimeRangeNavigator.RightTooltipStyle.MarginLeft = 15;
dateTimeRangeNavigator.RightTooltipStyle.MarginTop = 15;
dateTimeRangeNavigator.RightTooltipStyle.MarginRight = 15;
dateTimeRangeNavigator.RightTooltipStyle.MarginBottom = 15;
{% endhighlight %}

![](tooltip_images/tooltip_img3.png)


