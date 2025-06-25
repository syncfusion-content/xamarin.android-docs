---
layout: post
title: Customization in Syncfusion® Segmented Control for Xamarin.Android
description: Learn how to customize the text, border, scrolling, corner radius, and color in Xamarin.Android Segmented Control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Customization of Xamarin.Android Segmented Control

The Segmented Control supports customizing segment color, text color, icon size, selection color, and more. This control also supports enabling the segments to fit your application's theme. It can be customized in the following areas:

## Text Appearance

The text inside the Segmented Control can be customized by its font size, color, and font family.

### Font Family

You can customize the font family of the segmented item using the [`FontIconStyle`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_FontIconStyle) property.

{% highlight c# %}

segmentedControl.FontIconStyle = Typeface.Create("sans-serif-light", TypefaceStyle.Normal);

{% endhighlight %}

### Font Color

You can customize the text color of the segmented item using the [`FontColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_FontColor) property.

{% highlight c# %}

segmentedControl.FontColor = Color.Red;

{% endhighlight %}

![Font color customization in Segmented Control](images/Customization/Xamarin_Android_Fontcolor.png)

### Font Size

You can change the text size of the segmented item using the [`FontSize`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_FontSize) property.

{% highlight c# %}

segmentedControl.FontSize = 20;

{% endhighlight %}

![Font size customization in Segmented Control](images/Customization/Xamarin_Android_Size.png)

## Border

You can customize the border by its color and thickness.

### Border Color

You can customize the [`BorderColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_BorderColor) of all the items in the Segmented Control.

{% highlight c# %}

segmentedControl.BorderColor = Color.Red;

{% endhighlight %}

![Border color customization in Segmented Control](images/Customization/Xamarin_Android_Bordercolor.png)

### Border Thickness

You can customize the width of the border using the [`BorderThickness`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_BorderThickness) property.

{% highlight c# %}

segmentedControl.BorderThickness = 5;

{% endhighlight %}

![Border thickness customization in Segmented Control](images/Customization/Xamarin_Android_BorderThickness.png)

## Padding

The Segmented Control handles padding between the items.

### Segment Padding

Spacing between the segmented items in the control can be customized using the [`SegmentPadding`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SegmentPadding) property.

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

![Segment padding customization in Segmented Control](images/Customization/Xamarin_Android_Padding.png)

## Corner Radius

The Segmented Control provides corner radius support for the segmented items and strip.

### Item Radius

The Segmented Control customizes the corner radius for each segmented item.

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

![Segment corner radius customization in Segmented Control](images/Customization/Xamarin_Android_ItemCornerRadius.png)

### Selection Strip Radius

The Segmented Control customizes corner radius for the selection strip using the [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_CornerRadius) property of [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SelectionIndicatorSettings).

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    CornerRadius = 15
};

{% endhighlight %}

![Selected segment corner radius customization in Segmented Control](images/Customization/Xamarin_Android_SelectionstripRadius.png)

### Control Radius

The Segmented Control also handles corner radius for the border line of the whole control.

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

![Corner radius customization in Segmented Control](images/Customization/Xamarin_Android_controlRadius.png)

## Color

The Segmented Control allows users to customize the background color of the segmented items and background color of the control.

### Item Color

You can customize the background color of each segmented item using the [`Color`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentItem.html#Syncfusion_Android_Buttons_SfSegmentItem_BackgroundColor) property of [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SelectionIndicatorSettings).

{% highlight c# %}

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Color = Color.ParseColor("#FF355088")
};

{% endhighlight %}

![Segment item color customization in Segmented Control](images/Customization/Xamarin_Android_ItemCornerRadius.png)

### Control Color

You can customize the background color of the control by setting a value for the [`BackColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_BackColor) property.

{% highlight c# %}

segmentedControl.BackColor = Color.ParseColor("#02A0AE");

{% endhighlight %}

![Segmented Control color customization](images/Customization/Xamarin_Android_color.png)

## Scrolling in Segmented Control Programmatically

The Segmented Control allows programmatic scrolling based on index and item using the [`ScrollTo`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_ScrollTo_System_Int32_Syncfusion_Android_Buttons_ScrollToPosition_) methods mentioned as follows:

### ScrollTo(index, scrollToPosition)

This method is used to scroll the segment item based on the given index and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_ScrollToPosition) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(5, Syncfusion.Android.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

### ScrollTo(item, scrollToPosition)

This method is used to scroll the segment item based on the given data or [`SfSegmentItem`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentItem.html) and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(viewModel.Items[5], Syncfusion.Android.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}
