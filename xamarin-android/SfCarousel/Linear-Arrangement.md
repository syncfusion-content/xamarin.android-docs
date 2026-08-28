---
layout: post
title: Linear Arrangement in Syncfusion® Carousel control for Xamarin.Android
description: Learn how to arrange carousel items in linear layout using ViewMode property in Xamarin.Android platform
platform: xamarin.android
control: SfCarousel
documentation: ug
---

# Linear Arrangement

The Carousel items can be arranged in a stacked linear layout by setting the `ViewMode` property to `Linear`. The default option is `Default`, which displays items in the standard carousel arrangement.

{% highlight C# %}

SfCarousel carousel=new SfCarousel(this);
carousel.ViewMode = ViewMode.Linear;

{% endhighlight %}

N> It is important to include the Xamarin.Android.Support.v17.Leanback library to use the carousel linear mode on the Android platform.

![Linear arrangement](images/linear.png)

