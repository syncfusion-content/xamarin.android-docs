---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Appearance and Styling

SfRating control provides support to customize the Size, Item count and space between rating items.

## Set Size

The `ItemSize` property sets the size of the Rating items. 

N> By default, property value is 50.

{% tabs %}

{% highlight C# %}

	   rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSize.jpg)
 
## Set Space between Items

The `ItemSpacing` property sets the spacing between the Rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight C# %}

	   rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSpace.jpg)
 
## Set Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% tabs %}

{% highlight C# %}

	   rating.ItemCount=4;

{% endhighlight %}

{% endtabs %}

![](images/fourstar.jpg)

## Rating Settings

For styling customization, set the `RatingSettings` property value with `SfRatingSettings` object instance.


{% tabs %}

{% highlight C# %}

	SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.RatedFill = Color.FromHex("#fbd10a");
	
{% endhighlight %}

{% endtabs %}

After adding Rating settings, add the SfRatingSettings instance to Rating instance.


{% tabs %}

{% highlight C# %}

    rating.RatingSettings=ratingSettings;

{% endhighlight %}

{% endtabs %}