---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.Android
description: A quick tour to initial users on Syncfusion Rating control for Xamarin.Android platform
platform: Xamarin.Android
control: Rating
documentation: ug

---

# Getting Started

This section explains you the steps to configure a SfRating control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRating control.

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac

Add the following assembly references to the Android project,

[android\Syncfusion.SfRating.Andriod.dll]

## Add and Configure the SfRating Control

* Create an instance for SfRating control and adding to application.

{% tabs %}

{% highlight C# %}

SfRating rating=new SfRating(this);
SetContentView(rating);
	
{% endhighlight %}

{% endtabs %}

* Configure the properties of SfRating control.

{% tabs %}

{% highlight C# %}

rating.ItemCount=5;
rating.Precision = SFRatingPrecision.Half;
rating.ToolTipPlacement= SFRatingToolTipPlacement.None;
rating.ItemSize=10;
rating.Readonly=true;
rating.Value=(float)3.5;
rating.ItemSpacing = 5;

{% endhighlight %}

{% endtabs %}

## Set Value

* The `Value` property sets the display value of the Rating. 

N> By default, property value is 0.

{% tabs %}

{% highlight C# %}

rating.Value=3;

{% endhighlight %}

{% endtabs %}

## Precision

* To enable full, half and exact values of Rating, set the `Precision` property.

{% tabs %}

{% highlight C# %}

rating.Precision = Precision.Standard;

{% endhighlight%}

{% endtabs %}


![](images/gettingstarted.png)


