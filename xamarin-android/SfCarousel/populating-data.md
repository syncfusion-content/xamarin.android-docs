---
layout: post
title: Populating data in Syncfusion® Carousel control in Xamarin.Android
description: Learn details about how to set the DataSource, set the customview, adapter support and selected index in Carousel for Xamarin.Android platform
platform: xamarin.android
control: SfCarousel
documentation: ug
---

# Populating Data in Xamarin.Android Carousel (SfCarousel)

The `DataSource` property is used to populate the collection of SfCarouselItem, which can be either a collection of images or custom views.

## DataSource with collection of images

SfCarousel items can be populated with a collection of image data. For example, you may want to create a SfCarousel control that displays a list of images.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
	
List<SfCarouselItem> tempCollection = new List<SfCarouselItem>();

for (int i = 1; i <= 6; i++)
{
	SfCarouselItem sfCarouselItem = new SfCarouselItem(this);
	sfCarouselItem.ImageName = "image" + i.ToString();
	tempCollection.Add(sfCarouselItem);
}

carousel.SelectedIndex = 2;
carousel.DataSource = tempCollection;
SetContentView(carousel);

{% endhighlight %}

## DataSource with collection of custom views

The `ContentView` property is used to populate the carousel with a collection of custom views.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

List<SfCarouselItem> tempCollection = new List<SfCarouselItem>();

List<int> arrayList = new List<int>();
arrayList.Add(Resource.Drawable.image1);
arrayList.Add(Resource.Drawable.image2);
arrayList.Add(Resource.Drawable.image3);
arrayList.Add(Resource.Drawable.image4);


for (int i = 0; i <4; i++)
{
	FrameLayout frameLayout = new FrameLayout(this);
	SfCarouselItem sfCarouselItem = new SfCarouselItem(this);
	ImageView imageView = new ImageView(this);
	imageView.LayoutParameters = new Android.Views.ViewGroup.LayoutParams(carousel.ItemWidth, carousel.ItemHeight);
	imageView.SetImageResource(arrayList[i]);
	imageView.SetScaleType(ImageView.ScaleType.FitXy);
	frameLayout.AddView(imageView);
	sfCarouselItem.ContentView = frameLayout;
	tempCollection.Add(sfCarouselItem);
}

carousel.SelectedIndex = 2;

carousel.DataSource = tempCollection;

SetContentView(carousel);

{% endhighlight %}

## Adapter Support in Carousel control

Instead of providing a collection of SfCarouselItem objects, you can pass a single view that connects with a data source using the adapter pattern.

### Create an adapter class by inheriting CarouselAdapter

By extending the `CarouselAdapter` class, you can implement adapter support in Carousel using the `GetItemView` method.

{% highlight c# %}

public class AdapterTestingClass:CarouselAdapter
{
	Context context1;

	List<int> listOfArray;

	public AdapterTestingClass(Context context, List<int> arrayList)
	{
		context1 = context;
		listOfArray = arrayList;
	}

	public override Android.Views.View GetItemView(SfCarousel p0, int p1)
	{
		FrameLayout frameLayout = new FrameLayout(context1);
		SfCarouselItem sfCarouselItem = new SfCarouselItem(context1);
		ImageView imageView = new ImageView(context1);
		imageView.LayoutParameters = new Android.Views.ViewGroup.LayoutParams(p0.ItemWidth, p0.ItemHeight);
		imageView.SetImageResource(listOfArray[p1]);
		imageView.SetScaleType(ImageView.ScaleType.FitXy);
		frameLayout.AddView(imageView);
		return frameLayout;
	}
}
{% endhighlight %}

### Using the adapter class with Carousel

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

List<int> arrayList = new List<int>();
arrayList.Add(Resource.Drawable.image1);
arrayList.Add(Resource.Drawable.image2);
arrayList.Add(Resource.Drawable.image3);
arrayList.Add(Resource.Drawable.image4);

//Adapter class initialization

AdapterTestingClass testingClass = new AdapterTestingClass(this, arrayList);
carousel.Adapter = testingClass;

List<SfCarouselItem> carouselList = new List<SfCarouselItem>();
carouselList.Add(new SfCarouselItem(this));
carouselList.Add(new SfCarouselItem(this));
carouselList.Add(new SfCarouselItem(this));
carouselList.Add(new SfCarouselItem(this));

carousel.DataSource = carouselList;

carousel.SelectedIndex = 2;

SetContentView(carousel);
			
{% endhighlight %}

## SelectedIndex

The SelectedIndex property gets or sets the selected item index value of the SfCarousel control to bring a particular item to the center of the screen.

N> The `SelectedIndex` property will be 0 by default.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.SelectedIndex=2;

{% endhighlight %}

You can find a sample for loading images from SD card or internal storage to carousel view at this [link](https://github.com/SyncfusionExamples/how-to-load-image-from-sdcard-or-internal-storage-in-carousel-view-xamarin-android).
