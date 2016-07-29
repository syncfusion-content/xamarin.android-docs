---
layout: post
title: Getting Started with Syncfusion BusyIndicator control for Xamarin.Android
description: A quick tour to initial users on Syncfusion busyIndicator control for Xamarin.Android platform
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfBusyIndicator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfBusyIndicator control.

![](images/Getting-Started_img1.png)
                                                           
## Creating your first SfBusyIndicator in Xamarin.Android.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfBusyIndicator.Andriod.dll

### Add and Configure the SfBusyIndicator

* Adding reference to BusyIndicator.

{% highlight c# %}

	using Com.Syncfusion.BusyIndicator; 

{% endhighlight %}

* Create an instance of SfBusyIndicator.

{% highlight c# %}
	
	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
    SetContentView(busyIndicator);
	
{% endhighlight %}

### Set the AnimationType to SfBusyIndicator

To set AnimationType for the SfBusyIndicator, use `AnimationType` property and choose anyone of the 13 predefined animation types. 

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator (this); 
	busyIndicator.AnimationType=AnimationTypes.Battery;

{% endhighlight %}

### Configure the Properties in SfBusyIndicator

{% highlight c# %}
	
	busyIndicator.AnimationType=AnimationTypes.Ball;
	busyIndicator.TextColor=Color.RED;
	busyIndicator.ViewBoxHeight=20;
	busyIndicator.ViewBoxWidth=20;
	busyIndicator.IsBusy=True;
	
{% endhighlight %}



