---
layout: post
title:  Setting animation duration in Xamarin.Android Carousel
description: Learn how to set the duration for animation in Carousel for Xamarin.Android and customize timing properties
platform: xamarin.android
control: SfCarousel
documentation: ug
---

# Animation

The Duration property of the SfCarousel control specifies the time taken for the animation when an item moves to the selected position. The duration is specified in milliseconds. The default value is 300 milliseconds.
{% highlight C# %}

SfCarousel carousel= new SfCarousel(this);

carousel.Duration=500;

{% endhighlight %}

