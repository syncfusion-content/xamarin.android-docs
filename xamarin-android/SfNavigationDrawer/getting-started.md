---
layout: post
title: Getting Started with Syncfusion NavigationDrawer control for Xamarin.Android
description: A quick tour to initial users on Syncfusion NavigationDrawer control for Xamarin.Android platform
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NavigationDrawer for Xamarin.Android. You can walk through the entire process of creating an NavigationDrawer.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfNavigationDrawer.Andriod.dll

and 

Xamarin.Android.Support.v4 library (from Nuget Packages)

## Add SfNavigationDrawer

* Adding reference to NavigationDrawer.

{% tabs %}

{% highlight c# %}

using Com.Syncfusion.NavigationDrawer; 

{% endhighlight %}

{% endtabs %}

* Create an instance of SfNavigationDrawer.

{% tabs %}

{% highlight c# %}

SfNavigationDrawer navigationDrawer = new SfNavigationDrawer(this);
SetContentView(navigationDrawer);
	
{% endhighlight %}

{% endtabs %}

## Add Drawer Content

The sliding main content of the SfNavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% tabs %}

{% highlight c# %}

	List<String> list = new List<String>();
	list.Add("Home");
	list.Add("Profile");
	list.Add("Inbox");
	list.Add("Outbox");
	list.Add("Sent Items");
	list.Add("Trash");
	ArrayAdapter<String> arrayAdapter =new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1,list);
	listView.Adapter=arrayAdapter;
	listView.SetBackgroundColor(Color.White);
	listView.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent,ViewGroup.LayoutParams.MatchParent);
	contentLayout.AddView(listView);
	contentLayout.Orientation=Orientation.Vertical;
	FrameLayout frame = new FrameLayout (this);
	frame.LayoutParameters = new ViewGroup.LayoutParams (ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
	frame.SetBackgroundColor(Color.White);
	frame.AddView (contentLayout);
	//Add Drawer content view to Navigation
	navigationDrawer.DrawerContentView=frame;	

{% endhighlight %}

{% endtabs %}


## Add Drawer Header Content

SfNavigationDrawer provides option to display certain information like user id or names in the header part instead of providing everything in the drawer content view. 

This can be done using `DrawerHeaderView` property in SfNavigationDrawer.

{% tabs %}

{% highlight c# %}

	ImageView userImg= new ImageView(this);
	userImg.SetImageResource(R.drawable.user);
	userImg.SetBackgroundColor(Color.parseColor("#1aa1d6"));
	TextView userName= new TextView(this);
	userName.Text="James Pollock";
	userName.SetGravity(Gravity.CENTER);
	userName.TextSize=20;
	userName.SetBackgroundColor(Color.TRANSPARENT);
	userName.TextColor=Color.WHITE;
	LinearLayout headerLayout = new LinearLayout(this);
	headerLayout.Orientation=LinearLayout.VERTICAL;
	headerLayout.SetBackgroundColor(Color.parseColor("#1aa1d6"));
	headerLayout.SetGravity(Gravity.CENTER);
	headerLayout.SetPadding(0, 20, 0, 0);
	headerLayout.addView(userImg);
	headerLayout.AddView(userName);
	navigationDrawer.DrawerHeaderView=headerLayout;
 
{% endhighlight %}

{% endtabs %}

## Add Main Content

The main view of the SfNavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}

FrameLayout ContentFrame=new FrameLayout(this); 
ContentFrame.SetBackgroundColor(Color.WHITE);
ImageView img1 = new ImageView(this);
img1.SetImageResource(R.drawable.menu);
img1.SetScaleType(ImageView.ScaleType._FIT_XY_);
ContentFrame.SetBackgroundColor(Color.WHITE);
ContentFrame.AddView(img1);
navigationDrawer.ContentView=ContentFrame;

{% endhighlight %}

{% endtabs %}

![](images/getting-started.png)

## Set Drawing Edge for Drawer Panel

SfNavigationDrawer provides support to change the sliding position of the DrawerView panel. This can be set using `Position` property. The position can be any one of the following four options.

* Left

* Right

* Top

* Bottom

N> The default option is Left.

{% tabs %}

{% highlight c# %}

Position sliderposition = Position.Left;	
navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

## Change Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options,

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

{% tabs %}

{% highlight c# %} 

navigationDrawer.Transition=Transition.SlideOnTop;

{% endhighlight %}

{% endtabs %}
