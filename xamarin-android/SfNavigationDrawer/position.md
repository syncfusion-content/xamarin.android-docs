---
layout: post
title: Position of Drawer in Syncfusion® NavigationDrawer control for Xamarin.Android
description: Learn how to configure the position of the DrawerView panel and understand the best practices for different drawer positions.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---
# Configuring Drawer Position

The `Position` property determines from which edge of the screen the drawer panel will slide. This property provides flexibility in designing your navigation interface to match your application's layout and user experience requirements. The `Position` property supports four distinct options:
* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left

Sets the SfNavigationDrawer sliding position to the left.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Left;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![NavigationDrawer positioned on the left side](images/Left.png)

## Right

Sets the SfNavigationDrawer sliding position to the right.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Right;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![NavigationDrawer positioned on the right side](images/Right.png)
	
## Top

Sets the SfNavigationDrawer sliding position to the top.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Top;	
   	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![NavigationDrawer positioned at the top](images/Top.png)

## Bottom

Sets the SfNavigationDrawer sliding position to the bottom.

{% highlight c# %}

	Position sliderposition = Position.Bottom;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

![](images/bottom.png)







