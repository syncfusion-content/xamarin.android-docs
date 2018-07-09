---
layout: post
title: selection changed in Syncfusion Segmented control for Xamarin.Android
description: Learn how to handle selection changed in Segmented control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Selection changed

The segmented control handles the Selection changed when there is a change from one segment item to another. It can be handled by two ways.

## User interface

When users navigate from one item to another, selection is changed, so that the `SelectedIndex` value is updated to the new index of the item. The segmented control provides the `SelectionChanged` event, which is triggered when the selection is changed with the `SelectionChangedEventArgs`.

`Index` - Gets the current index value of the selected item.

{% highlight c# %}

segmentedControl.SelectionChanged += (object sender, SelectionChangedEventArgs e) => 
{
segmentedControl.BorderColor = Color.Red;
};

{% endhighlight %}

## Selected Index through programmatically.

You can set the default value programmatically for the selection to be placed. The selection gets updated based on the index value given for the `SelectedIndex`. 

{% highlight c# %}

segmentedControl.SelectedIndex = 2;

{% endhighlight %}


![](images/Selection-changed/selectionchange.png)


