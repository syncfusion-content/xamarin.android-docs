---
layout: post
title: AnimationTypes in Syncfusion® BusyIndicator for Xamarin.Android
description: Learn various animation types in SfBusyIndicator control and how to customize visual loading effects
platform: xamarin.android
control: SfBusyIndicator
documentation: ug
---

# AnimationType

The `AnimationType` property of SfBusyIndicator allows you to set any of the built-in animations for the SfBusyIndicator control. This property provides various predefined animation styles to enhance the visual appeal of the loading indicator.
{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.Ball;
	
{% endhighlight %}

{% endtabs %}

N> For getting animation types of SfBusyIndicator, need to add the `using Com.Syncfusion.Sfbusyindicator.Enums` namespace.

![Image of Ball animation type](images/Ball.png)
                                          

