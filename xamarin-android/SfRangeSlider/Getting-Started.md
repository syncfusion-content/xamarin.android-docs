---
layout: post
title: Getting Started with Syncfusion® RangeSlider Control for Xamarin.Android
description: A quick tour to initial users on Syncfusion® RangeSlider control for Xamarin.Android platform
platform: Xamarin.Android 
control: RangeSlider
documentation: ug
---

# Getting Started

This section explains the steps to configure a SfRangeSlider control in a real-world scenario and provides a walk-through of some customization features available in the SfRangeSlider control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders:

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly reference to the Android project:

android\Syncfusion.SfRangeSlider.Android.dll

## Add SfRangeSlider Control

Add the namespace for the assemblies:

{% tabs %}

{% highlight c# %}

	using Com.Syncfusion.RangeSlider; 

{% endhighlight %}

{% endtabs %}

* Now instantiate and add the SfRangeSlider control with a required optimal name.

{% tabs %}

{% highlight c# %}		

	SfRangeSlider rangeSlider = new SfRangeSlider(this);
	SetContentView(rangeSlider);

{% endhighlight %}

{% endtabs %}



## Restricting Values

The SfRangeSlider provides options to restrict the slider range between minimum and maximum values. The following code demonstrates how to set the range using the `Minimum` and `Maximum` properties:

{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	rangeSlider.DirectionReversed=false; 

{% endhighlight %}

{% endtabs %}

## Set Range

The SfRangeSlider supports both single thumb and double thumb modes. When using double thumb mode, each thumb value can be set using the `RangeStart` and `RangeEnd` properties.

N> The `ShowRange` property is used to switch between single thumb and double thumb modes. The `Orientation` property sets the orientation type.


{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	rangeSlider.DirectionReversed=false; 
	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 
	rangeSlider.Orientation=Orientation.Horizontal;

{% endhighlight %}

{% endtabs %}

## Ticks and Labels Customization

Ticks can be configured by setting the `TickFrequency` and `TickPlacement` properties. Value labels can be displayed by setting the `ShowValueLabel` property to `true`. The position of labels can be customized using the `LabelPlacement` property.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickFrequency=4; 
	rangeSlider.ShowValueLabel=true; 
	rangeSlider.ValuePlacement=ValuePlacement.TopLeft; 
	rangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

N> The TickFrequency determines the interval between the ticks.

## Adding Snapping Mode

The movement of the thumb can be controlled in different ways by setting the `SnapsTo` property. This allows the thumb to snap to specific positions for more precise value selection.


{% tabs %}

{% highlight c# %}

rangeSlider.SnapsTo=SnapsTo.Ticks; 
rangeSlider.StepFrequency=6;

{% endhighlight %}

{% endtabs %}

![](images/RangeSlider.png)
