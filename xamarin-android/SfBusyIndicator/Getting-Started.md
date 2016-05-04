---
layout: post
title: Getting Started with Syncfusion BusyIndicator control for Xamarin.Android
description: A quick tour to initial users on Syncfusion busyIndicator control for Xamarin.Android platform
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a BusyIndicator control in a real-time scenario and also provides a walk-through on some of the customization features available in BusyIndicator control.

![](images/Getting-Started_img1.png)
                                                           
## Creating your first BusyIndicator in Xamarin.Android.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfBusyIndicator.Andriod.dll

### Add and Configure the BusyIndicator

* Adding reference to busyindicator.

{% highlight c# %}

	using Com.Syncfusion.BusyIndicator; 

{% endhighlight %}

* Create an instance of BusyIndicator.

{% highlight c# %}
	
	SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);
    this.Content=sfBusyIndicator;
	
{% endhighlight %}

### Set the AnimationType to BusyIndicator

To set AnimationType for the BusyIndicator, use AnimationType property and choose anyone of the 13 predefined animation types. 

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator (this); 
	busyIndicator.AnimationType=AnimationTypes.Battery;

{% endhighlight %}

### Configure the Properties in BusyIndicator

{% highlight c# %}
	
	sfBusyIndicator.AnimationType=AnimationTypes.Ball;
	sfBusyIndicator.TextColor=Color.RED;
	sfBusyIndicator.ViewBoxHeight=20;
	sfBusyIndicator.ViewBoxWidth=20;
	sfBusyIndicator.IsBusy=True;
	
{% endhighlight %}



