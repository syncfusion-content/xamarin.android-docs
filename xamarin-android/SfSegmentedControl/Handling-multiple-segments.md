---
layout: post
title: Handling the Segments in Xamarin.Android Syncfusion® Segmented Control
description: Learn how to restrict the visible segment count and its available scrolling options in Xamarin.Android Segmented Control.
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Handling Multiple Segments in Xamarin.Android SfSegmentedControl

The Segmented Control handles the segmented items with the space distributed for the items in two ways:

## Visible Segment Count

The Segmented Control displays the items for the view based on the count that is given for [`VisibleSegmentsCount`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_VisibleSegmentsCount).

{% highlight c# %}

[C#]

segmentedControl.VisibleSegmentsCount = 4;
....
segmentedControl.ItemsSource = = new ObservableCollection<SfSegmentItem>
{
  new SfSegmentItem(){Text = "Item1"},          
  new SfSegmentItem(){Text = "Item2"},     
  new SfSegmentItem(){Text = "Item3"},  
  new SfSegmentItem(){Text = "Item4"},          
  new SfSegmentItem(){Text = "Item5"},     
  new SfSegmentItem(){Text = "Item6"},  
  new SfSegmentItem(){Text = "Item7"},          
};
   
{% endhighlight %}

![Xamarin.Android SfSegmentedControl with four visible segments](images/Handling-multiple-segments/visiblesegment.png)

## Scrolling

When the available space in the Segmented Control is not equally distributed, the items beyond the edges of the control can be viewed by scrolling the panel.
