---
layout: post
title: Customization in Syncfusion segmented control for Xamarin.Android
description: Learn how to customize the text, border, scrolling, corner radius, and color in Xamarin.Android SegmentedControl
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Customization of Xamarin.Android Segmented Control

The segmented control supports customizing segment color, text color, icon size, selection color, and more. This control also supports enabling the segments to fit your application’s theme. It can be customized in the following areas.

## Text appearance

The text inside the segmented control can be customized by its font size, color, and its font family.

### Font family

You can customize the font family of the segmented item using the [`FontIconStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~FontIconStyle.html) property.

{% highlight c# %}

segmentedControl.FontIconStyle= Typeface.Create("sans-serif-light", TypefaceStyle.Normal);

{% endhighlight %}

### Font color

You can customize the text color of the segmented item using the [`FontColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~FontColor.html) property.

{% highlight c# %}

segmentedControl.FontColor = Color.Red;

{% endhighlight %}

![Font color customization in segmented control](images/Customization/Xamarin_Android_Fontcolor.png)

### Font size

You can change the text size of the segmented item using the [`FontSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~FontSize.html) property.

{% highlight c# %}

segmentedControl.FontSize = 20;

{% endhighlight %}

![Font size customization in segmented control](images/Customization/Xamarin_Android_Size.png)

## Border

You can customize the border by their color and thickness.

### Border color

You can customize the [`BorderColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~BorderColor.html) of all the items in the segmented control.

{% highlight c# %}

segmentedControl.BorderColor = Color.Red;

{% endhighlight %}

![Border color customization in segmented control](images/Customization/Xamarin_Android_Bordercolor.png)

### Border thickness

You can customize the width of the border using the [`BorderThickness`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~BorderThickness.html) property.

{% highlight c# %}

segmentedControl.BorderThickness = 5;

{% endhighlight %}

![Border thickness customization in segmented control](images/Customization/Xamarin_Android_BorderThickness.png)

### Padding

The segmented control handles padding between the items.

#### Segment padding

Spacing between the segmented items in the control can be customized using the [`SegmentPadding`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~SegmentPadding.html).

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

![Segment padding customization in segmented control](images/Customization/Xamarin_Android_Padding.png)

### Corner radius

The segmented control provides corner radius support for the segmented items and strip.

#### Item radius

The segmented control customizes the corner radius for each segmented item.

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

![Segment corner radius customization in segmented control](images/Customization/Xamarin_Android_ItemCornerRadius.png)

#### Selection strip radius

The segmented control customizes corner radius for selection strip using the [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~CornerRadius.html) property of [`SelectionIndicatorSetting`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~SelectionIndicatorSettings.html).

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.CornerRadius = 15;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selected segment corner radius customization in segmented control](images/Customization/Xamarin_Android_SelectionstripRadius.png)

#### Control radius

The segmented control also handles corner radius for border line of the whole control.

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

![Corner radius customization in segmented control](images/Customization/Xamarin_Android_controlRadius.png)

### Color

The segmented control allows users to customize the background color of the segmented items and background color of the control.

#### Item color

You can customize the background color of each segmented item using the [`Color`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentItem~BackgroundColor.html) property of [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~SelectionIndicatorSettings.html).

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.ParseColor("#FF355088");
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Segment item color customization in segmented control](images/Customization/Xamarin_Android_ItemCornerRadius.png)

#### Control color

You can customize the background color of the control by setting value for the [`BackColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~BackColor.html) property.

{% highlight c# %}

segmentedControl.BackColor = Color.ParseColor("#02A0AE");

{% endhighlight %}

![Segmented control color customization in segmented control](images/Customization/Xamarin_Android_color.png)

## Scrolling in segmented control programmatically

The SegmentedControl allows programmatic scrolling based on index and item using the [`ScrollTo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~ScrollTo.) methods mentioned as follows.

### ScrollTo(index, scrollToPosition)

This method is used to scroll the segment item based on given index and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~ScrollToPosition.html) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(5, Syncfusion.Android.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

### ScrollTo(item, scrollToPosition)

This method is used to scroll the segment item based on the given data or [`SfSegmentItem`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentItem.html) and [`ScrollToPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.ScrollToPosition.html) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(viewModel.Items[5], Syncfusion.Android.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}