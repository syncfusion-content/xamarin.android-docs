---
layout: post
title: Various features of Syncfusion® NavigationDrawer control for Xamarin.Android
description: Learn how to configure the main content view in NavigationDrawer, including setup, customization, and best practices for content management.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Setting Main Content

The SfNavigationDrawer consists of two primary components: the [Main Content](#main-content) area and the [Drawer Panel Content](/xamarin-android/SfNavigationDrawer/Drawer-Content "Sliding Panel Content"). This document focuses on configuring the main content area, which serves as the primary interface that users interact with when the drawer is closed.
## Main Content

The main content area displays your application's primary interface and can be configured using the `ContentView` property. This property accepts any Android view or layout that you want to display as the main content.

### Basic Implementation

The following example demonstrates how to set up a basic main content area with an image view:
{% tabs %}

{% highlight c# %}

namespace navigationDrawerSample
{
	[Activity(Label = "navigationDrawerSample", MainLauncher = true, Icon = "@mipmap/icon")]
	public class MainActivity : Activity
	{
           SfNavigationDrawer navigationDrawer;
           protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            
            navigationDrawer = new SfNavigationDrawer(this);
            FrameLayout ContentFrame=new FrameLayout(this); 
            ContentFrame.SetBackgroundColor(Android.Graphics.Color.White);
            ImageView userImg = new ImageView(this);
            userImg.SetImageResource(Resource.Drawable.Icon);
            userImg.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            ContentFrame.AddView(userImg);
            navigationDrawer.ContentView=ContentFrame;
			SetContentView(navigationDrawer);
		}
	}
}
	
{% endhighlight %}

{% endtabs %}
	
![NavigationDrawer main content configuration](images/Content-View.png)

