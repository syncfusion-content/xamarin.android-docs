---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.Android
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Setting Main Content

The SfNavigationDrawer is mainly divided into two parts, such as [Main Content](#main-content) and  [Drawer Panel Content](/xamarin-android/SfNavigationDrawer/Drawer-Content "Sliding Panel Content")

## Main Content

The main view of the SfNavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}

FrameLayout ContentFrame=new FrameLayout(this); 
ContentFrame.SetBackgroundColor(Color.WHITE);
ImageView img1 = new ImageView(this);
img1.SetImageResource(R.drawable._menu_);
img1.SetScaleType(ImageView.ScaleType._FIT_XY_);
ContentFrame.SetBackgroundColor(Color.WHITE);
ContentFrame.AddView(img1);
navigationDrawer.ContentView=ContentFrame;
	
{% endhighlight %}

{% endtabs %}
	
![](images/Content-View.png)

