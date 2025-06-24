---
layout: post
title: Setting the duration for animation in Syncfusion® Carousel control in Xamarin.Android
description: Learn how to set the duration for animation in Carousel for Xamarin.Android
platform: Xamarin.Android
control: SfCarousel
documentation: ug
---

# Animation

The [Duration](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfCarousel.Android.SfCarousel.html#Syncfusion_SfCarousel_Android_SfCarousel_Duration) property of the SfCarousel control specifies the time taken for the animation when an item moves to the selected position. The duration is specified in milliseconds. The default value is 300 milliseconds.
{% highlight C# %}

SfCarousel carousel= new SfCarousel(this);

carousel.Duration=500;

{% endhighlight %}

