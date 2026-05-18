---
layout: post
title: IsBusy support in Syncfusion® BusyIndicator for Xamarin.Android
description: Learn how to enable and disable animation in BusyIndicator control to manage loading states effectively
platform: xamarin.android
control: SfBusyIndicator
documentation: ug
---

# Make Busy Animation Idle

The SfBusyIndicator control provides support to control whether the animation should be running. The `IsBusy` property determines the visibility and animation state of the busy indicator.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.SingleCircle;
	busyIndicator.IsBusy=true;

{% endhighlight %}

{% endtabs %}

![IsBusy Image](images/IsBusy_img1.png)

BusyIndicator
{:.caption}



