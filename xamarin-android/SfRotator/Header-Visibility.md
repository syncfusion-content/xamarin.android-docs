---
layout: post
title: Syncfusion® Rotator Text Area Visibility for Xamarin.Android
description: Learn how to enable and customize the text area visibility feature in Rotator control for Xamarin.Android platform
platform: xamarin.android 
control: Rotator
documentation: ug
---

# Header Visibility

The `TextVisible` property can be used to enable the text area visibility in bottom area of SfRotator for providing additional information of items. TextVisible property is used to change the visibility of the Text panel that is displayed when SfRotatorItem collection is set.

N> By default, the property value is false.

{% highlight C# %}

Context context = this;

SfRotator rotator = new SfRotator(context);

List<SfRotatorItem> collection = new List<SfRotatorItem>();

for(int i = 1; i < 5; i++)
{
	SfRotatorItem item = new SfRotatorItem(context);
	item.ImageContent = "movie" + i;
	collection.Add(item);
}

// Assign the collection to the rotator's data source
rotator.DataSource = collection;

// Used Resource folder images's name will display at the bottom of Rotator control.

rotator.TextVisible = true;

rotator.SelectedIndex = 2;

SetContentView(rotator);

{% endhighlight %}

