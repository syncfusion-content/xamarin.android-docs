---
layout: post
title: Sizing support in Syncfusion BusyIndicator control for Xamarin.Android
description: Learn how to customize the size of the animation type
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Sizing

ViewBox is used for sizing an animation.It is achieved by,

* ViewBoxHeight
* ViewBoxWidth

`ViewBoxHeight` allows you to set the height of the animation and `ViewBoxWidth` allows to set the width of the animation.

{% highlight c# %}

	SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.SlicedCircle;
	busyIndicator.ViewBoxWidth=200;
	busyIndicator.ViewBoxHeight=200;
	
{% endhighlight %}

![](images/Sizing_img1.png)                                                                              

ViewBox height and width
{:.caption}
