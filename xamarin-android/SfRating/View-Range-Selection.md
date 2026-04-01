---

layout: post
title: Range Selection in Syncfusion® SfRating for Xamarin.Android
description: Learn how to perform range selection with custom views in the Rating control using EnableViewRangeSelection property.
platform: xamarin.android
control: Rating
documentation: ug

---

# View Range Selection

When using custom views in SfRating, by default only the selected item displays its rated state while other items remain in their unrated state. The `EnableViewRangeSelection` property allows you to change the visual behavior so that all items up to the selected rating display their rated state, creating a continuous range selection effect.

N> The EnableViewRangeSelection property is used only for CustomViews. 

{% tabs %}

{% highlight C# %}

SfRating rating;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);

    --------

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;

    --------

}

{% endhighlight %}

{% endtabs %}

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
