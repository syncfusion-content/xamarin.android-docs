---
layout: post
title: Thumb customization for DateTimeRangeNavigator
description: Thumb customization
platform: Xamarin.Android
control: SfDateTimeRangeNavigator
documentation: ug
---

# Thumb

The [`LeftThumbStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~LeftThumbStyle.html) and [`RightThumbStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~RightThumbStyle.html) properties are used to configure the left and right thumb of the `SfDateTimeRangeNavigator`. Following properties are available in thumb style to configure left and right thumb individually. 

* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~StrokeColor.html) – used to change the stroke color of the thumb.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~BackgroundColor.html) – used to change the background color of the thumb.
* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~StrokeWidth.html) – used to change the stroke width of the thumb.
* [`Width`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~Width.html) – used to change the width of the thumb.
* [`Height`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~Height.html) – used to change the height of the thumb.
* [`LineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~LineColor.html) – used to change the line color of the thumb.
* [`LineWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~LineWidth.html) – used to change the line width of the thumb.
* [`LinePathEffect`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ThumbStyle~LinePathEffect.html) – used to change the dash array of the thumb line.

{% highlight c# %}
[C#]
SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator(this);
...
rangeNavigator.LeftThumbStyle.BackgroundColor = Color.Aqua;
rangeNavigator.LeftThumbStyle.StrokeColor = 0x083928;
rangeNavigator.LeftThumbStyle.StrokeWidth = 3;
rangeNavigator.LeftThumbStyle.LineColor = 0xE70E49;
rangeNavigator.LeftThumbStyle.LineWidth = 5;
rangeNavigator.RightThumbStyle.BackgroundColor = Color.Aqua;
rangeNavigator.RightThumbStyle.StrokeColor = 0x083928;
rangeNavigator.RightThumbStyle.StrokeWidth = 3;
rangeNavigator.RightThumbStyle.LineColor = 0xE70E49;
rangeNavigator.RightThumbStyle.LineWidth = 5;
{% endhighlight %}

![](thumb_images/thumb_img1.png)


