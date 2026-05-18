---
layout: post
title: Selection Changed in Syncfusion® Segmented Control for Xamarin.Android
description: Learn how to notify the selection changes on its segments in Xamarin.Android Segmented Control (SfSegmentedControl).
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Notify the Selection Changes in SfSegmentedControl in Xamarin.Android

The Segmented Control handles the selection changed event when there is a change from one segment item to another. It can be handled in two ways:

## User Interface

When users navigate from one item to another, the selection is changed, so the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SelectedIndex) value is updated to the new index of the item. The Segmented Control provides the [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html) event, which is triggered when the selection is changed with the [`SelectionChangedEventArgs`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SelectionChangedEventArgs.html).

[`Index`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SelectionChangedEventArgs.html#Syncfusion_Android_Buttons_SelectionChangedEventArgs_Index) - Gets the current index value of the selected item.

{% highlight c# %}

segmentedControl.SelectionChanged += (object sender, SelectionChangedEventArgs e) => 
{
    var selectedIndex = e.Index;
};

{% endhighlight %}

## Selected Index Through Programming

You can set the default value programmatically for the selection to be placed. The selection gets updated based on the index value given for the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SelectedIndex) property.

{% highlight c# %}

segmentedControl.SelectedIndex = 2;

{% endhighlight %}


![Xamarin.Android SfSegmentedControl with selection of second item](images/Selection-changed/selectionchange.png)


