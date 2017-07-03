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

SfRating rating= new SfRating(this);

SfRatingItem item = new SfRatingItem(this);

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

	ImageView iv = new ImageView(this);
	iv.SetImageResource(Resource.Drawable.Angry_selected);
	item.SelectedView = iv;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating item.

{% highlight C# %}

	ImageView iv1 = new ImageView(this);
	iv1.SetImageResource(Resource.Drawable.Angry_Unselected);
	item.UnSelectedView = iv1;

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

	List<SfRatingItem> listof = new List<SfRatingItem>();
	listof.Add(item);
	rating.Items = listof;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating items. 

{% highlight C# %}

	SfRating rating = new SfRating(this);
	SfRatingItem item = new SfRatingItem(this);
		ImageView iv = new ImageView(this);
		iv.SetImageResource(Resource.Drawable.Angry_selected);			
		item.SelectedView = iv;
		ImageView iv1 = new ImageView(this);
		iv1.SetImageResource(Resource.Drawable.Angry_Unselected);	
		item.UnSelectedView = iv1;

	SfRatingItem item1 = new SfRatingItem(this);
		ImageView iv2 = new ImageView(this);
		iv2.SetImageResource(Resource.Drawable.UnHappy_selected);
		item1.SelectedView = iv2;
		ImageView iv3 = new ImageView(this);
		iv3.SetImageResource(Resource.Drawable.UnHappy_Unselected);
		item1.UnSelectedView = iv3;

	SfRatingItem item2 = new SfRatingItem(this);
		ImageView iv4 = new ImageView(this);
		iv4.SetImageResource(Resource.Drawable.Neutral_selected);
		item2.SelectedView = iv4;
		ImageView iv5 = new ImageView(this);
		iv5.SetImageResource(Resource.Drawable.Neutral_Unselected);
		item2.UnSelectedView = iv5;

	SfRatingItem item3 = new SfRatingItem(this);
		ImageView iv6 = new ImageView(this);
		iv6.SetImageResource(Resource.Drawable.Happy_selected);
		item3.SelectedView = iv6;
		ImageView iv7 = new ImageView(this);
		iv7.SetImageResource(Resource.Drawable.Happy_Unselected);
		item3.UnSelectedView = iv7;

	SfRatingItem item4 = new SfRatingItem(this);
		ImageView iv8 = new ImageView(this);
		iv8.SetImageResource(Resource.Drawable.Excited_selected);
		item4.SelectedView = iv8;
		ImageView iv9 = new ImageView(this);
		iv9.SetImageResource(Resource.Drawable.Excited_Unselected);
		item4.UnSelectedView = iv9;

	List<SfRatingItem> listof = new List<SfRatingItem>();
		listof.Add(item);
		listof.Add(item1);
		listof.Add(item2);
		listof.Add(item3);
		listof.Add(item4);
	rating.Items = listof;
	rating.EnableCustomView = true;

{% endhighlight %}

![](images/CustomviewItems.png)
 




 
