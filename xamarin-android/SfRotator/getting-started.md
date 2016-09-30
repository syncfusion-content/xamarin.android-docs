---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Android platform
platform: Xamarin.Android 
control: Rotator 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRotator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRotator control.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfRotator.Andriod.dll

and 

Xamarin.Android.Support.v17.Leanback library (from Nuget Packages)


## Add SfRotator 

* Adding namespace for the added assemblies.

{% tabs %}

{% highlight c# %}

	using Com.Syncfusion.Rotator; 

{% endhighlight %}

{% endtabs %}

* Now add the SfRotator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}		

SfRotator  rotator  = new SfRotator(this);
SetContentView(rotator);

{% endhighlight %}

{% endtabs %}

## Set Navigation Mode

SfRoator provides option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using `NavigationMode` property.

{% tabs %}

{% highlight C# %}	

	rotator.NavigationMode = NavigationMode.Dots;

{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using `TabStripPosition` property.  

{% tabs %}

{% highlight C# %}	

rotator.NavigationMode = NavigationMode.Dots;
rotator.TabStripPosition = TabStripPosition.Bottom;
	
{% endhighlight %}

{% endtabs %}


## Add Data Collection

SfRotator items can be populated with a collection of image data. This collection includes Arrays, Lists and DataTables. For example you may wants to create a Rotator model with Image as follows.

{% tabs %}

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

{% endtabs %}

![](images/rotator.png)