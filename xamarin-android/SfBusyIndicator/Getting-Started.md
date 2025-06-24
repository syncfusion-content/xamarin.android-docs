---
layout: post
title: Getting Started with Xamarin.Android BusyIndicator Control| Syncfusion®
description: Learn here about Getting Started with Syncfusion® Essential® Xamarin.Android BusyIndicator Control, its elements, and more.
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Getting Started with Xamarin.Android BusyIndicator

This section explains the steps to configure a SfBusyIndicator control in a real-time scenario and provides a walk-through of some customization features available in the SfBusyIndicator control.
                                                 
## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders:

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly reference to the Android project:

android\Syncfusion.SfBusyIndicator.Android.dll

## Add SfBusyIndicator

The following steps help you add a SfBusyIndicator control through code.

* Add the namespace for the added assemblies.

{% tabs %}

{% highlight c# %}

using Com.Syncfusion.SfBusyIndicator;

{% endhighlight %}

{% endtabs %}

* Now add the SfBusyIndicator control with the required optimal name using the included namespace.

{% tabs %}

{% highlight c# %}
	
SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
SetContentView(busyIndicator);
	
{% endhighlight %}

{% endtabs %}

## Setting Animation Type

SfBusyIndicator provides 10 predefined animation types such as Ball, Battery, Globe, and more. You can select any one of the animation types using the `AnimationType` property.

The following example demonstrates the battery type animation for SfBusyIndicator:

{% tabs %}

{% highlight c# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator (this); 
busyIndicator.AnimationType = AnimationTypes.Battery;

{% endhighlight %}

{% endtabs %}

## Configure Properties in SfBusyIndicator

You can customize the height, width, and text color properties in SfBusyIndicator as follows:

{% tabs %}

{% highlight c# %}
	
busyIndicator.AnimationType=AnimationTypes.Ball;
busyIndicator.TextColor=Color.Red;
busyIndicator.ViewBoxHeight=20;
busyIndicator.ViewBoxWidth=20;
busyIndicator.IsBusy=true;
	
{% endhighlight %}

{% endtabs %}

![Xamarin.Android BusyIndicator getting started](images/Getting-Started_img1.png)

