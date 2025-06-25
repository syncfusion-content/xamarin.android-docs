---
layout: post
title: Interaction in Syncfusion® Carousel Control in Xamarin.Android
description: Learn how to perform an operation while changing the carouselItem or Collection in Carousel for Xamarin.Android
platform: xamarin.android
control: SfCarousel
documentation: ug
---

# How to perform an operation while changing the carousel item?

You can perform an operation while changing the carousel item using the `SelectionChanged` event. The SelectionChanged event returns the SfCarouselItem with the changed index.

{% highlight C# %}

carousel.SelectionChanged += (object sender, SfCarousel.SelectionChangedEventArgs e) =>
{
   
};

{% endhighlight %}

## How to perform an operation while changing the collection of carousel?

You can perform an operation while changing the collection of carousel using the `ItemsCollectionChanged` event. The ItemsCollectionChanged event returns the changed collection of SfCarouselItem.

{% highlight C# %}

carousel.ItemsCollectionChanged += (object sender SfCarousel.ItemsCollectionChangedEventArgs e) =>
    {
    
    };

{% endhighlight %}

