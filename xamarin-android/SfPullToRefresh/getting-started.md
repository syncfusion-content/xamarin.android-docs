---
layout: post
title: Getting Started | PullToRefresh |Xamarin.Android | Syncfusion
description: getting started
platform:Xamarin.Android
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


## Customizing a simple SfPulToRefresh sample

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

