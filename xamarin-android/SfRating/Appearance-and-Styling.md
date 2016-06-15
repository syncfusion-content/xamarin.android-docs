---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Appearance and Styling

## Item Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% highlight C# %}

	   rating.ItemSize=20;

{% endhighlight %}

![](images/layoutSize.jpg)
 
## Item Spacing

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% highlight C# %}

	   rating.ItemSpacing=20;

{% endhighlight %}

![](images/layoutSpace.jpg)
 
## Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% highlight C# %}

	   rating.ItemCount=4;

{% endhighlight %}

![](images/fourstar.jpg)

## Read Only

Rating control provides support to restrict or enable changing of rating value using `ReadOnly` property. 

N> By default, property value is set to False.

{% highlight C# %}

	   rating.ReadOnly= true;

{% endhighlight %}

![](images/readOnly.jpg)

## Rating Settings

For styling customization, set the `RatingSettings` property value with `SfRatingSettings` object instance.

The `SfRatingSettings` object contains following list of properties.

1. RatedFill
2. RatedStroke
3. RatedStrokeThickness
4. UnRatedFill
5. UnRatedStroke
6. UnRatedStrokeThickness

{% highlight C# %}

	SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.RatedFill = Color.FromHex("#fbd10a");
    rating.RatingSettings=ratingSettings;

{% endhighlight %}

### Rated Fill

The `RatedFill` property fills the rated area with the specified solid color.

{% highlight C# %}

	ratingSettings.RatedFill=Color.FromHex("#fbd10a");

{% endhighlight %}

![](images/ratedFill.jpg)

### Rated Stroke

The `RatedStroke` property sets the stroke for the rated area with the specified solid color.

{% highlight C# %}

	ratingSettings.RatedStroke=Color.GREEN;

{% endhighlight %}

![](images/ratedStroke.jpg)
 
### Rated Stroke Thickness

The `RatedStrokeThickness` property sets the stroke thickness for the rated area with the specified value.

{% highlight C# %}

	ratingSettings.RatedStrokeThickness=3;

{% endhighlight %}

![](images/ratedStrokeThickness.jpg)
 
### UnRated Fill

The `UnRatedFill` property fills the unrated area with the specified solid color.

{% highlight C# %}

	ratingSettings.UnRatedFill=Color.GRAY;

{% endhighlight %}

![](images/unRatedFill.jpg)

### UnRated Stroke

The `UnRatedStroke` property sets the stroke for the unrated area with the specified solid color.

{% highlight C# %}

	ratingSettings.UnRatedStroke=Color.BLACK;

{% endhighlight %}

![](images/unRatedStroke.jpg)

### UnRated Stroke Thickness

The `UnRatedStrokeThickness` property sets the stroke thickness for the unrated area with the specified value.

{% highlight C# %}

	ratingSettings.UnRatedStrokeThickness=3;

{% endhighlight %}

![](images/unRatedStrokeThickness.jpg)
