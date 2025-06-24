---
layout: post
title: Populating data in Syncfusion® Rotator control in Xamarin.Android
description: Learn how to set the DataSource in Rotator for Xamarin.Android
platform: Xamarin.Android
control: Rotator
documentation: ug
---

# Populating Data

The SfRotator control provides flexible options for populating content through its `DataSource` property. You can display various types of content including images, custom views, or complex layouts. The control supports multiple approaches for data population, each suited to different scenarios and requirements.

## Data Population Approaches

The SfRotator offers three primary methods for populating data:

1. **ImageContent Approach**: Simple image display using resource names
2. **Custom Content Approach**: Complex layouts with multiple UI elements
3. **Adapter Pattern**: Advanced customization with RotatorAdapter
## Using ImageContent 

The `ImageContent` property provides the simplest way to display images in the SfRotator. This approach is ideal for basic image galleries where you want to display images from your application's resources.

### Basic ImageContent Implementation
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

// Assign the collection to the rotator's DataSource
rotator.DataSource = collection;

rotator.SelectedIndex = 2;

SetContentView(rotator);

{% endhighlight %}

![Simple Image Rotator](images/rotator.png)

## Using Content

`Content` property in RotatorItem helps to view the Rotator from any of custom view. 

{% highlight C# %}

Context context = this;

SfRotator rotator = new SfRotator(context);

// Collection of RotatorItem

List<SfRotatorItem> collection = new List<SfRotatorItem>();

// Resource of ImageView in RotatorItem's Content

int[] images = { Resource.Drawable.movie1, Resource.Drawable.movie2, Resource.Drawable.movie3, Resource.Drawable.movie4, Resource.Drawable.movie5 };

// Resource of Button in RotatorItem's Content

string[] strings = { "ImageView1", "ImageView2", "ImageView3", "ImageView4", "ImageView5" };

for (int i = 0; i < 5; i++)
{
	SfRotatorItem sfRotatorItem = new SfRotatorItem(context);
	LinearLayout linearLayout = new LinearLayout(context);
	linearLayout.Orientation = Orientation.Vertical;
	ImageView imageView = new ImageView(context);
	imageView.SetImageResource(images[i]);
	Button button = new Button(context);
	button.Text = strings[i];
	button.TextSize = 33;
	button.SetBackgroundColor(Android.Graphics.Color.BurlyWood);
	linearLayout.AddView(button);
	linearLayout.AddView(imageView);
	sfRotatorItem.Content = linearLayout;
	collection.Add(sfRotatorItem);
}

// Assign the collection of custom view  Rotator's DataSource

rotator.DataSource = collection;

rotator.SelectedIndex = 2;

SetContentView(rotator);

{% endhighlight %}

![](images/content.png)

# Through RotatorAdapter

RotatorAdapter object acts as a bridge between an RotatorAdapterView and the underlying data for that view. The Adapter provides access to the data items. The Adapter is also responsible for making a View for each item in the data set.

Needed things to achieve this,

* `DataSource` - Determines the count of custom view will reflect on Rotator control
* `Adapter` - This property will carry the custom view on Rotator.
* `CustomAdapter Class`- Which inherits the RotatorAdapter class and use the GetItemView and GetThumbnailView method.

### CustomAdapter Class

{% highlight C# %}

public class AdapterClass :RotatorAdapter
{
	Context context;
	int[] collectionOfImages;

	// Override method to get the Dotted view Rotator control.

	public override Android.Views.View GetItemView(SfRotator p0, int p1)
	{

		ImageView imageView = new ImageView(con1);
		imageView.SetImageResource(collectionOfImages[p1]);
		return imageView;
	} 
	// Override method to get the Thumbnail view Rotator control.
		
	public override Android.Views.View GetThumbnailView(SfRotator p0, int p1)
	{
		ImageView imageView = new ImageView(con1);
		imageView.SetImageResource(collectionOfImages[p1]);
		return imageView;
	}
	public AdapterClass(Context con,int [] list)
	{
		context = con;
		collectionOfImages = list;
	}

}

{% endhighlight %}

### In MainActivity.cs

{% highlight C# %}

public class MainActivity : Activity
{
	protected override void OnCreate(Bundle savedInstanceState)
	{
		
	base.OnCreate(savedInstanceState);

	Context context = this;

	SfRotator rotator = new SfRotator(context);

	List<SfRotatorItem> collection = new List<SfRotatorItem>();
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));

	// Determines the count of custom view will reflect on Rotator control

	rotator.DataSource = collection;

	// Resources of used custom view in Adapter

	int[] images = { Resource.Drawable.movie1, Resource.Drawable.movie2, Resource.Drawable.movie3, Resource.Drawable.movie4, Resource.Drawable.movie5 };

	rotator.SelectedIndex = 2;

	// RotatorAdapter usage

	rotator.Adapter = new AdapterClass(this,images);

	SetContentView(rotator);

	}
}

{% endhighlight %}

![](images/rotator.png)

