---
layout: post
title: IsBusy support in Syncfusion BusyIndicator control for Xamarin.Android
description: Learn how to enable and disable animation in BusyIndicator
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# IsBusy

The `IsBusy` property in the SfBusyIndicator control is used to determine whether an animation needs to be executed or not.

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.SingleCircle;
	busyIndicator.IsBusy=true;

{% endhighlight %}

![](images/IsBusy_img1.png)                                                                                                   

BusyIndicator
{:.caption}


