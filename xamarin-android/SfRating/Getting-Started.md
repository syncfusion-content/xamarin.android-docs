---

layout: post
title: Getting Started with Xamarin.Android Rating Control | Syncfusion®
description: Learn here about getting started with Syncfusion® Essential® Xamarin.Android Rating control, and more.
platform: Xamarin.Android
control: Rating
documentation: ug

---

# Getting Started with Xamarin.Android Rating Control

This section explains how to configure the SfRating control in a real-world scenario and provides a walk-through of some customization features available in the SfRating control.

## Referencing Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders:

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in an unzipped package location on Mac.

Add the following assembly reference to the Android project:

[android\Syncfusion.SfRating.Andriod.dll]

## Add and Configure the SfRating Control

* The following namespace needs to be added.

{% tabs %}

{% highlight C# %}

using Com.Syncfusion.Rating;
	
{% endhighlight %}

{% endtabs %}

Create an instance of the SfRating control and add it to your application:

{% tabs %}

{% highlight C# %}

SfRating rating;
protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    rating = new SfRating(this);
    SetContentView(rating);
}
	
{% endhighlight %}

{% endtabs %}

## Set Number of Rating Items

The number of rating items to be displayed can be customized in the SfRating control. You can create a rating application with 5 items as follows:

N> The default value of this property is 5.

{% tabs %}

{% highlight C# %}

rating.ItemCount = 5;

{% endhighlight %}

{% endtabs %}

## Set Value

The display value can be set in the SfRating control, which represents the selected rating among the items. The following code sample demonstrates how to set a display value of 3 with 5 rating items:

N> The default value of this property is 0.

{% tabs %}

{% highlight C# %}

rating.Value=3;

{% endhighlight %}

{% endtabs %}

## Set Precision

To enable full, half, and exact values of rating, set the `Precision` property.

{% tabs %}

{% highlight C# %}

rating.Precision = Precision.Standard;

{% endhighlight %}

{% endtabs %}

![SfRating application](images/gettingstarted.png)

The complete Getting Started sample is available in this [documentation](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfRating_GettingStarted-436521212.zip).

