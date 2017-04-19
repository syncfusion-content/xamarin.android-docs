---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Android 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.Android 
control: Rotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

## Horizontal

Items can be navigated in horizontal direction.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

## Vertical

Items can be navigated in vertical direction.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

