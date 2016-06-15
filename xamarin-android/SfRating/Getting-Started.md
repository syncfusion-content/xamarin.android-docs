---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.Android
description: A quick tour to initial users on Syncfusion Rating control for Xamarin.Android platform
platform: Xamarin.Android
control: Rating
documentation: ug

---

# Getting Started

This section explains you the steps to configure a rating control in a real-time scenario and also provides a walk-through on some of the customization features available in Rating control.

![](images/gettingstarted.png)

## Creating your first Rating in Xamarin.Android

### Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac

Add the following assembly references to the Android project,

[android\Syncfusion.SfRating.Andriod.dll]

### Add and Configure the Rating Control

* Create an instance for rating control and adding to application.

{% highlight C#%}

		SfRating rating=new SfRating(this);
		SetContentView(rating);
	
{% endhighlight %}

* Configure the properties of Rating control.

{% highlight C# %}

	rating.ItemCount=5;
	rating.Precision = SFRatingPrecision.Half;
	rating.ToolTipPlacement= SFRatingToolTipPlacement.None;
	rating.ItemSize=10;
	rating.Readonly=true;
	rating.Value=(nfloat)3.5;
	rating.ItemSpacing = 5;

{% endhighlight %}

### Setting Value

* The `Value` property sets the display value of the rating. 

N> By default, property value is 0.

{% highlight C# %}

    rating.Value=3;

{% endhighlight %}

### Precision

* To enable full, half and exact values of rating, set the `Precision` property.

{% highlight C#%}

    rating.Precision = Precision.Standard;

{% endhighlight%}

![](images/standard.jpg)


