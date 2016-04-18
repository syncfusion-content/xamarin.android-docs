---
layout: post
title: Getting Started with syncfusion rangeslider control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion rangeSlider control for Xamarin.Android platform
platform: Xamarin.Android 
control: RangeSlider
documentation: ug
---

# Getting Started

This section explains you the steps to configure a RangeSlider control in a real-time scenario and also provides a walk-through on some of the customization features available in RangeSlider control.

![](images/RangeSlider.png)

## Creating your first RangeSlider in Xamarin.Android

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfRangeSlider.Andriod.dll


### Add and Configure the RangeSlider

* Adding reference to rangeSlider.

{% highlight c# %}

	using Com.Syncfusion.RangeSlider; 

{% endhighlight %}


* Create an instance of SfRangeSlider.


{% highlight c# %}		

	SfRangeSlider sfRangeSlider = new SfRangeSlider(this);
	SetContentView(sfRangeSlider);

{% endhighlight %}

### Add Values and Scale

You can set the minimum value for the slider by using the `setMinimum()` and `setMaximum()` properties in the RangeSlider. It can be Numerical values.

{% highlight c# %}

	range.Minimum=0; 
	range.Maximum=24; 
	range.DirectionReversed=false; 
	range.RangeEnd=20; 
	range.RangeStart=4;
	range.ShowRange=true; 
	range.Orientation=Orientation.Horizontal;

{% endhighlight %}

N> Likewise, `RangeStart` and `RangeEnd` can be set that denote the start range and end range values while dual thumb is used. The `ShowRange` property is used to switch between a single thumb and double thumb. The `Orientation` property sets the type of orientation.

### Add Ticks and Labels for RangeSlider

The ticks can be set by setting the `TickFrequency` and `TickPlacement`. Likewise, value labels can be set by setting the `ShowValueLabel` property to true. The position of label can be varied by the `LabelPlacement` property.

{% highlight c# %}

	range.TickFrequency=4; 
	range.ShowValueLabel=true; 
	range.ValuePlacement=ValuePlacement.TopLeft; 
	range.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

N> The TickFrequency determines the interval between the ticks.

### Add Snapping Type for RangeSlider

The movement of the thumb can be varied in different ways. This is achieved by setting the SnapsTo property.

{% highlight c# %}

	range.SnapsTo=SnapsTo.Ticks; 
	range.StepFrequency=6;

{% endhighlight %}

### Configure the Properties in RangeSlider

{% highlight c# %}

	SfRangeSlider sfRangeSlider = new SfRangeSlider ();
	sfRangeSlider.Minimum=0;
	sfRangeSlider.Maximum=24;
	sfRangeSlider.RangeStart=4;
	sfRangeSlider.RangeEnd=20;
	sfRangeSlider.TickFrequency=4;
	sfRangeSlider.TickPlacement=TickPlacement.Outside;
	sfRangeSlider.SnapsTo=SnapsTo.Ticks;
	sfRangeSlider.ValuePlacement=ValuePlacement.TopLeft;
	sfRangeSlider.ShowRange=True;

{% endhighlight %}