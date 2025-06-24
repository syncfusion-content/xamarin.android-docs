---
layout: post
title: Adding Custom Items in Syncfusion® Rating Control for Xamarin.Android
description: Learn how to add custom items and views to the Syncfusion Rating control for enhanced user experience
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Custom Views

The SfRating control provides support for adding custom views to create personalized rating experiences with custom graphics and layouts.
## Add SfRating Control

Initialize the SfRating control and SfRatingItem with an appropriate namespace reference.
{% highlight C# %}

SfRating rating;
SfRatingItem ratingItem;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    rating = new SfRating(this);
    ratingItem = new SfRatingItem(this);
}

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property applies a custom view to the selected rating item state.

{% highlight C# %}

    ImageView angrySelected = new ImageView(this);
    angrySelected.SetImageResource(Resource.Drawable.Angry_selected);
    ratingItem.SelectedView = angrySelected;

{% endhighlight %}

## Set Unselected View
 
The `UnSelectedView` property applies a custom view to the unselected rating item state.

{% highlight C# %}

    ImageView angryUnselected = new ImageView(this);
    angryUnselected.SetImageResource(Resource.Drawable.Angry_Unselected);
    ratingItem.UnSelectedView = angryUnselected;

{% endhighlight %}

## Add Items to Collection

The `Items` property holds the collection of SfRatingItem objects that define the rating scale.

N> Each SfRatingItem maintains both selected and unselected view states.
{% highlight C# %}

    List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
    ratingItemList.Add(ratingItem);
    rating.Items = ratingItemList;

{% endhighlight %}

## Enable Custom Items

When the `EnableCustomView` property is set to true, the control displays the custom items configured in the rating collection.

{% highlight C# %}

    SfRating rating = new SfRating(this);
    SfRatingItem angry = new SfRatingItem(this);
    ImageView angrySelected = new ImageView(this);
    angrySelected.SetImageResource(Resource.Drawable.Angry_selected);			
    angry.SelectedView = angrySelected;
    ImageView angryUnselected = new ImageView(this);
    angryUnselected.SetImageResource(Resource.Drawable.Angry_Unselected);	
    angry.UnSelectedView = angryUnselected;

    SfRatingItem unhappy = new SfRatingItem(this);
    ImageView unhappySelected = new ImageView(this);
    unhappySelected.SetImageResource(Resource.Drawable.UnHappy_selected);
    unhappy.SelectedView = unhappySelected;
    ImageView unhappyUnselected = new ImageView(this);
    unhappyUnselected.SetImageResource(Resource.Drawable.UnHappy_Unselected);
    unhappy.UnSelectedView = unhappyUnselected;

    SfRatingItem neutral = new SfRatingItem(this);
    ImageView neutralSelected = new ImageView(this);
    neutralSelected.SetImageResource(Resource.Drawable.Neutral_selected);
    neutral.SelectedView = neutralSelected;
    ImageView neutralUnselected = new ImageView(this);
    neutralUnselected.SetImageResource(Resource.Drawable.Neutral_Unselected);
    neutral.UnSelectedView = neutralUnselected;

    SfRatingItem happy = new SfRatingItem(this);
    ImageView happySelected = new ImageView(this);
    happySelected.SetImageResource(Resource.Drawable.Happy_selected);
    happy.SelectedView = happySelected;
    ImageView happyUnselected = new ImageView(this);
    happyUnselected.SetImageResource(Resource.Drawable.Happy_Unselected);
    happy.UnSelectedView = happyUnselected;

    SfRatingItem exited = new SfRatingItem(this);
    ImageView exitedSelected = new ImageView(this);
    exitedSelected.SetImageResource(Resource.Drawable.Excited_selected);
    exited.SelectedView = exitedSelected;
    ImageView exitedUnselected = new ImageView(this);
    exitedUnselected.SetImageResource(Resource.Drawable.Excited_Unselected);
    exited.UnSelectedView = exitedUnselected;

    List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
    ratingItemList.Add(angry);
    ratingItemList.Add(unhappy);
    ratingItemList.Add(neutral);
    ratingItemList.Add(happy);
    ratingItemList.Add(exited);
    rating.Items = ratingItemList;
    rating.EnableCustomView = true;

{% endhighlight %}

![Custom Rating Item](images/CustomviewItems.png)
 