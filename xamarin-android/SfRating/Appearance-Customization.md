---
layout: post
title: Appearance Customization in Syncfusion® Rating Control for Xamarin.Android
description: Learn how to customize the appearance and styling of the Rating control using fill colors, stroke colors, and stroke width properties through SfRatingSettings.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Appearance Customization
You can customize the color, stroke width, and stroke color of rated and unrated items using the following properties of `SfRatingSettings`:

* `RatedFill`
* `UnRatedFill`
* `RatedStroke`
* `UnRatedStroke`
* `RatedStrokeWidth`
* `UnRatedStrokeWidth`

## Rating Settings

For customizing styles, set the `RatingSettings` property with an `SfRatingSettings` object instance.

{% tabs %}

{% highlight C# %}

SfRating rating;
SfRatingSettings ratingSettings;
protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    rating = new SfRating(this);
    ratingSettings = new SfRatingSettings();
    rating.RatingSettings = ratingSettings;
}

{% endhighlight %}

{% endtabs %}

## Set Fill Color

The SfRating control supports setting fill colors for rated and unrated items.

### Rated Items

The `RatedFill` property fills the rated area with the specified solid color.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedFill = Color.Red;

{% endhighlight %}

{% endtabs %}

![Rated Items](images/ratedFill.jpg)

### Unrated Items

The `UnRatedFill` property fills the unrated area with the specified solid color.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedFill = Color.Gray;

{% endhighlight %}

{% endtabs %}

![Unrated Items](images/unRatedFill.jpg)

## Set Stroke Color

The SfRating control supports setting stroke colors for rated and unrated items.

### Rated Items

The `RatedStroke` property sets the stroke color for rated items.

{% tabs %}

{% highlight C# %}

    ratingSettings.RatedStroke = Color.DarkGreen;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Color](images/ratedStroke.png)

### Unrated Items

The `UnRatedStroke` property sets the stroke color for unrated items.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStroke = Color.Black;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Color](images/unRatedStroke.jpg)
 
## Set Stroke Width

The SfRating control supports setting stroke width for rated and unrated items.

### Rated Items

The `RatedStrokeWidth` property sets the stroke width for rated items.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedStrokeWidth = 3;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Width](images/ratedStrokeWidth.jpg)

### Unrated Items

The `UnRatedStrokeWidth` property sets the stroke width for unrated items.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStrokeWidth = 3;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Width](images/unRatedStrokeWidth.jpg)
