---
layout: post
title: Getting Started with Syncfusion® Carousel Control for Xamarin.Android
description: A quick tour to initial users on Syncfusion® carousel control for Xamarin.Android platform.
platform: Xamarin.Android
control: SfCarousel
documentation: ug
---

# Getting Started

This section explains the steps to configure a SfCarousel control in a real-time scenario and provides a walk-through of some customization features available in the SfCarousel control.

## Referencing Essential Studio<sup>®</sup> components in your solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders:

{Syncfusion Installed location}\Essential Studio\15.x.x.x\lib

Add the following assembly references to the Android project:

android\Syncfusion.SfCarousel.Android.dll

and 

Xamarin.Android.Support.v17.Leanback library (from NuGet Packages)

## Add SfCarousel

The SfCarousel control is configured entirely in C# code. The following steps explain how to create a SfCarousel and configure its elements:

* Adding namespace for the added assemblies. 

{% highlight C# %}

using Com.Syncfusion.Carousel;

{% endhighlight %}

* Now add the SfCarousel control with a required optimal name using the included namespace.

{% highlight C# %}

SfCarousel carousel=new SfCarousel(this);
SetContentView(carousel);

{% endhighlight %}

## Set Gap between Items

SfCarousel provides an option to set the distance between items in the panel. This can be accomplished using the `Offset` property in the SfCarousel control.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.Offset=20;

{% endhighlight %}

## Tilt Non-Selected Items

Items in the SfCarousel control can be rotated at a user-defined angle. The `RotationAngle` property is used to specify the angle at which items should be rotated.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.RotationAngle = 45;

{% endhighlight %}

## Setting DataSource

SfCarousel items can be populated with a collection of image data. For example, you may want to create a SfCarousel control that displays a list of images.

{% highlight c# %}

List<SfCarouselItem> tempCollection = new List<SfCarouselItem>();

for (int i = 1; i <= 6; i++)
{
	SfCarouselItem sfCarouselItem = new SfCarouselItem(this);
	sfCarouselItem.ImageName = "image" + i.ToString();
	tempCollection.Add(sfCarouselItem);
}

carousel.SelectedIndex = 2;
carousel.DataSource = tempCollection;

{% endhighlight %}

### Setting the height and width of carousel items

The `ItemHeight` and `ItemWidth` properties are used to change the height and width of carousel items in the carousel panel.

{% highlight C# %}

SfCarousel sfCarousel=new SfCarousel(this);
sfCarousel.ItemWidth=150;
sfCarousel.ItemHeight=170;

{% endhighlight %}

## SelectedIndex

You can bring a particular item to the center of the screen using the `SelectedIndex` property in the SfCarousel control.

N> The `SelectedIndex` property will be 0 by default.

{% highlight c# %}

SfCarousel carousel=new SfCarousel(this);
carousel.SelectedIndex=2;

{% endhighlight %}

![Carousel](images/carousel.png)

You can find the complete getting started sample from this [Link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedSampleCarousel39791457)
