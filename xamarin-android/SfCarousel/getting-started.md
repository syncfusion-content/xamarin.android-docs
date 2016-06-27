---
layout : post
title : Getting Started with Syncfusion Carousel Control for Xamarin.Android
description : A quick tour to initial users on Syncfusion carousel control for Xamarin.Android platform.
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a Carousel control in a real-time scenario and also provides a walk-through on some of the customization features available in Carousel control.

![](images/carousel.png)

## Creating your first Carousel in Xamarin.Android

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfCarousel.Andriod.dll

and 

Xamarin.Android.Support.v17.Leanback library (from Nuget Packages)

## Add and Customize the Carousel Control

The Carousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Carousel and configure its elements,

* Adding reference to carousel.

{% highlight C# %}

	using Com.Syncfusion.Carousel; 

{% endhighlight %}

* Create an instance for SfCarousel.

{% highlight C# %}

	SfCarousel carousel=new SfCarousel(this);
	SetContentView(carousel);

{% endhighlight %}

## Setting Offset

Set the Offset property to specify the distance between the items in Carousel panel.

{% highlight C# %}

	SfCarousel carousel = new SfCarousel(this);
	carousel.SelectedIndex=2;
	carousel.Offset=20;

{% endhighlight %}


## Setting Rotation Angle

Set the RotationAngle property to decide the angle in which items should be rotated.

{% highlight C# %}

	SfCarousel carousel = new SfCarousel(this);
	carousel.SelectedIndex=2;
	carousel.Offset=20;
	carousel.RotationAngle = 45;

{% endhighlight %}

## Setting DataSource

SfCarousel items can be populated with a collection of image data. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight c# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.ImageName="image"+i;
	temp.add(item);
	}
	carousel.DataSource=temp;

{% endhighlight %}

