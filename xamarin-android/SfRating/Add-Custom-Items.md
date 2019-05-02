---
layout: post
title: Adding Custom items in Syncfusion Rating Itmes control for Xamarin.Android
description: Learn how to add the Custom Items in rating control
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Custom Views

SfRating Items control provides support to add custom views.

## Add SfRating Items

Add the SfRating Items control with a required optimal name by using the included namespace.

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
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

	ImageView customImageView1 = new ImageView(this);
	customImageView1.SetImageResource(Resource.Drawable.Angry_selected);
	ratingItem.SelectedView = customImageView1;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating item.

{% highlight C# %}

	ImageView customImageView2 = new ImageView(this);
	customImageView2.SetImageResource(Resource.Drawable.Angry_Unselected);
	ratingItem.UnSelectedView = customImageView2;

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

	List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
	ratingItemList.Add(ratingItem);
	rating.Items = ratingItemList;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating items. 

{% highlight C# %}

	SfRating rating = new SfRating(this);
	SfRatingItem ratingItem = new SfRatingItem(this);
		ImageView customImage1 = new ImageView(this);
		customImage1.SetImageResource(Resource.Drawable.Angry_selected);			
		ratingItem.SelectedView = customImage1;
		ImageView customImage2 = new ImageView(this);
		customImage2.SetImageResource(Resource.Drawable.Angry_Unselected);	
		ratingItem.UnSelectedView = customImage2;

	SfRatingItem ratingItem1 = new SfRatingItem(this);
		ImageView customImage3 = new ImageView(this);
		customImage3.SetImageResource(Resource.Drawable.UnHappy_selected);
		ratingItem1.SelectedView = customImage3;
		ImageView customImage4 = new ImageView(this);
		customImage4.SetImageResource(Resource.Drawable.UnHappy_Unselected);
		ratingItem1.UnSelectedView = customImage4;

	SfRatingItem ratingItem2 = new SfRatingItem(this);
		ImageView customImage5 = new ImageView(this);
		customImage4.SetImageResource(Resource.Drawable.Neutral_selected);
		ratingItem2.SelectedView = customImage5;
		ImageView customImage6 = new ImageView(this);
		customImage6.SetImageResource(Resource.Drawable.Neutral_Unselected);
		ratingItem2.UnSelectedView = customImage6;

	SfRatingItem ratingItem3 = new SfRatingItem(this);
		ImageView customImage7 = new ImageView(this);
		customImage7.SetImageResource(Resource.Drawable.Happy_selected);
		ratingItem3.SelectedView = customImage7;
		ImageView customImage8 = new ImageView(this);
		customImage8.SetImageResource(Resource.Drawable.Happy_Unselected);
		ratingItem3.UnSelectedView = customImage8;

	SfRatingItem ratingItem4 = new SfRatingItem(this);
		ImageView customImage9 = new ImageView(this);
		customImage9.SetImageResource(Resource.Drawable.Excited_selected);
		ratingItem4.SelectedView = customImage9;
		ImageView customImage10 = new ImageView(this);
		customImage10.SetImageResource(Resource.Drawable.Excited_Unselected);
		ratingItem4.UnSelectedView = customImage10;

	List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
		ratingItemList.Add(ratingItem);
		ratingItemList.Add(ratingItem1);
		ratingItemList.Add(ratingItem2);
		ratingItemList.Add(ratingItem3);
		ratingItemList.Add(ratingItem4);
	rating.Items = ratingItemList;
	rating.EnableCustomView = true;

{% endhighlight %}

![Custom Rating Item](images/CustomviewItems.png)
 