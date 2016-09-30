---
layout : post
title : Getting Started with Syncfusion Carousel Control for Xamarin.Android
description : A quick tour to initial users on Syncfusion carousel control for Xamarin.Android platform.
platform : Xamarin.Android
control : SfCarousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a SfCarousel control in a real-time scenario and also provides a walk-through on some of the customization features available in SfCarousel control.

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfCarousel.Andriod.dll

and 

Xamarin.Android.Support.v17.Leanback library (from Nuget Packages)

## Add SfCarousel

The SfCarousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfCarousel and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

using Com.Syncfusion.Carousel; 

{% endhighlight %}

{% endtabs %}

* Now add the SfCarousel control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

SfCarousel carousel=new SfCarousel(this);
SetContentView(carousel);

{% endhighlight %}

{% endtabs %}

## Set Gap between Items

SfCarousel provides option to set the distance between the items in the panel. This can be done by using the `Offset` property in SfCarousel control.

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.SelectedIndex=2;
carousel.Offset=20;

{% endhighlight %}

{% endtabs %}


## Tilt Non Selected Items

Items in the SfCarousel control can be rotated in user defined angle. `RotationAngle` property is used to decide the angle in which items should be rotated.

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.SelectedIndex=2;
carousel.Offset=20;
carousel.RotationAngle = 45;

{% endhighlight %}

{% endtabs %}

## Setting DataSource

SfCarousel items can be populated with a collection of image data. For example, a user may want to create a SfCarousel control which will display a list of images.

{% tabs %}

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

{% endtabs %}

## SelectedIndex

We can bring particular item to the center of the screen using `SelectedIndex` property in SfCarousel control.

N> The `SelectedIndex` property will be 0 by default.

{% tabs %}

{% highlight c# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

{% endtabs %}

![](images/carousel.png)