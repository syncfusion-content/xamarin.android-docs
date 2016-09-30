---
layout : post
title : Populating data in Syncfusion Carousel control in Xamarin.Android
description : Learn how to set the DataSource in Carousel for Xamarin.Android
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# Populating Data

SfCarousel control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## DataSource

SfCarousel items can be populated with a collection of image data. For example, a user may wants to create a SfCarousel control which will display a list of images.

{% tabs %}

{% highlight c# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.ImageName="image"+i;
	temp.add(item);
	}
	carousel.DataSource=temp;

{% endhighlight %}

{% endtabs %}

## SelectedIndex

It gets or sets the Selected Item index value of SfCarousel control to bring the particular item to center of the screen.

N> The `SelectedIndex` property will be 0 by default.

{% tabs %}

{% highlight c# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

{% endtabs %}

