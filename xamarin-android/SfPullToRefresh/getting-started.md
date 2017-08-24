---
layout: post
title: Getting Started | PullToRefresh |Xamarin.Android | Syncfusion
description: getting started
platform: Xamarin.Android
control: PullToRefresh
documentation: ug
--- 

# Getting Started

## Create your first SfPullToRefresh in Xamarin.Android

This section encompasses on how to create a PullToRefresh that lets you to refresh the current content of the application. 

### Referring Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

 [android\<.SfPullToRefresh.Andriod.dll]

### Initializing PullToRefresh   
Refer to the following code to add the SfPullToRefresh control:

{% tabs %}

{% highlight c# %}
 
    protected override void OnCreate (Bundle savedInstanceState)
    {
    base.OnCreate (savedInstanceState);
    SfPullToRefresh pullToRefresh = new SfPullToRefresh();
    SetContentView (pullToRefresh);
    }



{% endhighlight %}

{% endtabs %}


## Customizing a simple SfPullToRefresh sample

To develop an application with Android PullToRefresh is simple. The following steps explains how to create and configure its properties.

1. Create the `PullableContent` for the `SfPullToRefresh`

You can set the `PullableContent` for the `SfPullToRefresh` by adding the desired UIElement.

{% tabs %}

{% highlight c# %}
   
    LinearLayout layout = new LinearLayout (context);
    layout.SetBackgroundColor (Color.AliceBlue);
    pullToRefresh.PullableContent = layout;

{% endhighlight %}

{% endtabs %}

## Events

The pulling event will be notified whenever the swipe gesture is started. This event will notify the listener each and every time until the refresh content height exceeds. When we release the gesture from pullable content, Refreshing event will be triggered. Now user can proceed to fetching the data from web or database. Once the data is fetched, we should call Refresh to method to complete all animations.

There are three built-in events in the PullToRefresh control namely:

1. `Pulling`
2. `Refreshing`
3. `Refreshed`

### Pulling

`Pulling` event is triggered when we start pulling down the PullableContent. It is triggered as long as the pointer or finger is pressed and the progress is less than 100 and not equal to 0 . The arguments for the event are:

* SfPullToRefresh
* Progress

{% tabs %}

{% highlight c# %}

    pullToRefresh.Pulling+= (object sender, SfPullToRefresh.PullingEventArgs e) => {
				
			};
			
{% endhighlight %}

{% endtabs %}

### Refreshing

`Refreshing` event is triggered once the content is pulled through the PullingThreshold or Progress reaches 100. This event is triggered till the Refresh() method is called.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Refreshing += (object sender, EventArgs e) => {
				
			};

{% endhighlight %}

{% endtabs %}

### Refreshed

`Refreshed` event is triggered once the refreshing and all the animations associated with the control are completed.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Refreshed += (object sender, EventArgs e) =>
			 {
  
				 if (selectedLayout != null)
				{
					handler.PostDelayed(() =>
					 {
						 System.Random random = new System.Random();
						 int i = random.Next(20, 50);
						 textView3 = (TextView)view.FindViewById(Resource.Id.text);
						 textView3.Text = i + "°".ToString() + "/12";
						 pullToRefresh.Refresh();
					 }, 2000);
				 }
			 };
{% endhighlight %}

{% endtabs %}
