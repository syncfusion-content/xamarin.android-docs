---
layout: post
title: Auto-scrolling the Syncfusion® Segmented Control for Xamarin.Android
description: Learn how to auto-scroll to the selected index in the Segmented Control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Auto-scrolling the Selected Segment Item

Auto-scrolling for selected item changes can be enabled by setting the [`AutoScrollSelectedItem`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_AutoScrollSelectedItem) property to `true`. You can control the scroll position of the segment item using the [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_ScrollToPosition) property. The default value for [`AutoScrollSelectedItem`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_AutoScrollSelectedItem) is `false`, and the default value for [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_ScrollToPosition) is [`MakeVisible`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html#Syncfusion_Android_Buttons_ScrollToPosition_MakeVisible). The following options are available for [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_ScrollToPosition):

* [`MakeVisible`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html#Syncfusion_Android_Buttons_ScrollToPosition_MakeVisible) - Scrolls to the selected segment item to make it visible in the control. If the item is already visible, scrolling will not occur.
* [`Start`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html#Syncfusion_Android_Buttons_ScrollToPosition_Start) - Scrolls to position the selected segment item at the start of the control.
* [`Center`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html#Syncfusion_Android_Buttons_ScrollToPosition_Center) - Scrolls to position the selected segment item at the center of the control.
* [`End`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.ScrollToPosition.html#Syncfusion_Android_Buttons_ScrollToPosition_End) - Scrolls to position the selected segment item at the end of the control.
{% tabs %}

{% highlight c# %}

segmentedControl.SelectedIndex = 5;

segmentedControl.AutoScrollSelectedItem = true;

segmentedControl.ScrollToPosition = Syncfusion.Android.Buttons.ScrollToPosition.Center;

{% endhighlight %}

{% endtabs %}