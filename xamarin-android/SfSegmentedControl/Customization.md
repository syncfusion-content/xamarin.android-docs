---
layout: post
title: Various customization in Syncfusion segmented control for Xamarin.Android
description: Learn how to customize the segmented control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Customization

The segmented control supports customizing segment color, text color, icon size, selection color, and more. This control also supports enabling the segments to fit your application’s theme. It can be customized in the following areas.

## Text appearance

The text inside the segmented control can be customized by its font size, color, and its font family.

### Font family

You can customize the font family of the segmented item using the `FontIconStyle` property.

{% highlight c# %}

segmentedControl.FontIconStyle= Typeface.Create("sans-serif-light", TypefaceStyle.Normal);

{% endhighlight %}

### Font color

You can customize the text color of the segmented item using the `FontColor` property.

{% highlight c# %}

segmentedControl.FontColor = Color.Red;

{% endhighlight %}

![](images/Customization/Xamarin_Android_Fontcolor.png)

### Font size

You can change the text size of the segmented item using the `FontSize` property.

{% highlight c# %}

segmentedControl.FontSize = 20;

{% endhighlight %}

![](images/Customization/Xamarin_Android_Size.png)

## Border

You can customize the border by their color and thickness.

### Border color

You can customize the border color of all the items in the segmented control.

{% highlight c# %}

segmentedControl.BorderColor = Color.Red;

{% endhighlight %}

![](images/Customization/Xamarin_Android_Bordercolor.png)

### Border thickness

You can customize the width of the border using the `BorderThickness` property.

{% highlight c# %}

segmentedControl.BorderThickness = 5;

{% endhighlight %}

![](images/Customization/Xamarin_Android_BorderThickness.png)

### Padding

The segmented control handles padding between the items.

#### Segment padding

Spacing between the segmented items in the control can be customized using the `SegmentPadding`.

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

![](images/Customization/Xamarin_Android_Padding.png)

### Corner radius

The segmented control provides corner radius support for the segmented items and strip.

#### Item radius

The segmented control customizes the corner radius for each segmented item.

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

![](images/Customization/Xamarin_Android_ItemCornerRadius.png)

#### Selection strip radius

The segmented control customizes corner radius for selection strip using the `CornerRadius` property of `SelectionIndicatorSetting`.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.CornerRadius = 15;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![](images/Customization/Xamarin_Android_SelectionstripRadius.png)

#### Control radius

The segmented control also handles corner radius for border line of the whole control.

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

![](images/Customization/Xamarin_Android_controlRadius.png)

### Color

The segmented control allows users to customize the background color of the segmented items and background color of the control.

#### Item color

You can customize the background color of each segmented item using the `Color` property of `SelectionIndicatorSettings`.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.ParseColor("#FF355088");
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![](images/Customization/Xamarin_Android_ItemCornerRadius.png)

#### Control color

You can customize the background color of the control by setting value for the `Color` property.

{% highlight c# %}

segmentedControl.Color = Color.ParseColor("#02A0AE");

{% endhighlight %}

![](images/Customization/Xamarin_Android_color.png)




