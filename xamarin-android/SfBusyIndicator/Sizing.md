---
layout: post
title: Sizing support in Syncfusion® BusyIndicator control for Xamarin.Android
description: Learn how to customize the size and dimensions of the BusyIndicator animation
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Sizing

You can customize the display size of the SfBusyIndicator control to fit your application's layout requirements. The `ViewBoxHeight` and `ViewBoxWidth` properties allow you to set the height and width dimensions of the animation area, giving you precise control over how the busy indicator appears in your user interface.
{% tabs %}

{% highlight c# %}

SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);
busyIndicator.AnimationType=AnimationTypes.SlicedCircle;
busyIndicator.ViewBoxWidth=200;
busyIndicator.ViewBoxHeight=200;
	
{% endhighlight %}

{% endtabs %}

![](images/Sizing_img1.png)                                                                              

ViewBox height and width
{:.caption}

