---
layout: post
title: Appearance and Styling in Syncfusion® Rating for Xamarin.Android
description: Learn how to customize the appearance and styling of the Rating control using ItemSize, ItemSpacing, ItemCount, and RatingSettings properties.
platform: xamarin.android
control: Rating
documentation: ug
---

# Appearance and Styling

When the default appearance doesn't meet your requirements, you can customize the view of the Xamarin.Android SfRating control. The SfRating control provides support for customizing the size, item count, and spacing between rating items.

## Set Item Size

The `ItemSize` property sets the size for individual rating items.

N> The default value of this property is 50.

{% tabs %}

{% highlight C# %}

	   rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![ Rating Item Size](images/layoutSize.jpg)
 
## Set Space Between Items

The `ItemSpacing` property sets the spacing between rating items.

N> The default value of this property is 5.

{% tabs %}

{% highlight C# %}

	   rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![Space between Rating Items](images/layoutSpace.jpg)
 
## Set Number of Items

The `ItemCount` property sets the number of rating items to be displayed.

N> The default value of this property is 5.

 {% tabs %}

{% highlight C# %}

	   rating.ItemCount = 4;

{% endhighlight %}

{% endtabs %}

![Rating item customization](images/fourStar.jpg)

## Rating Settings

For advanced styling customization, configure the `RatingSettings` property with an `SfRatingSettings` object instance.

{% tabs %}

{% highlight c# %}

SfRatingSettings ratingSettings = new SfRatingSettings();
ratingSettings.RatedFill = Color.Gray;

{% endhighlight %}

{% endtabs %}

After adding `RatingSettings` add the RatingSettings instance to `SfRating` instance.

{% tabs %}

{% highlight c# %}

rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}
