---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Android platform
platform: Xamarin.Android 
control: Rotator 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Rotator control in a real-time scenario and also provides a walk-through on some of the customization features available in Rotator control.

![](images/rotator.png)

## Creating your first Rotator in Xamarin.Android

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfRotator.Andriod.dll


## Add and Configure the Rotator 

* Adding reference to Rotator.

{% highlight c# %}

	using Com.Syncfusion.Rotator; 

{% endhighlight %}


* Create an instance of SfRotator.


{% highlight c# %}		

	SfRotator  rotator  = new SfRotator();
	SetContentView(rotator);

{% endhighlight %}

## Setting Navigation Mode

The NavigationMode property decides the navigation mode for navigating items. The items can be navigated using Thumbnail or Dots.

{% highlight C# %}	

	rotator.NavigationMode = NavigationMode.Dots;

{% endhighlight %}

## Customizing Position

The TabStripPosition property decides the position in which navigation strip items such as Thumbnail or Dots should be rendered. 

{% highlight C# %}	

	rotator.NavigationMode = NavigationMode.Dots;
	rotator.TabStripPosition = TabStripPosition.Bottom;
	
{% endhighlight %}

## Setting DataSource

SfRotator items can be populated with a collection of image data. For example, a user may want to create a SfRotator control which will display a sequence of images.

{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfRotatorItem item =new SfRotatorItem ();
	item.ImageName="image"+i;
	temp.add(item);
	}
	rotator.DataSource=temp;

{% endhighlight %}