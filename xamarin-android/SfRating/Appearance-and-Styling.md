---
layout: post
title: Appearance and Styling in Syncfusion SfRating control
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Appearance and Styling

When default view is not needed we can customize the view of Xamarin.Forms SfRating control. SfRating control provides support to customize the Size, Item count and space between rating items.

## Set Size

The `ItemSize` property sets the size of the Rating items. 

N> By default, property value is 50.

{% tabs %}

{% highlight C# %}

	   rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![ Rating Item Size](images/layoutSize.jpg)
 
## Set Space between Items

The `ItemSpacing` property sets the spacing between the Rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight C# %}

	   rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![Space between Rating Items](images/layoutSpace.jpg)
 
 ## Set Number of Items

 The `ItemCount` property sets the number of rating items to be displayed. 

 N> The default property value is 5.

 {% tabs %}

{% highlight C# %}

	   rating.ItemCount = 4;

{% endhighlight %}

{% endtabs %}

![Rating Item Customization](images/fourStar.jpg)