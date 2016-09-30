---
layout: post
title: NavigationMode of Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to view the different navigation modes of the Rotator control in Xamarin.Forms
platform: Xamarin.Forms 
control: Rotator
documentation: ug
---

# Navigation Modes

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image data can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

{% endtabs %}

![](images/thumbnail.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

{% endtabs %}

![](images/dots.png)

## Items / Dot Strip Positions

The `NavigationStripPosition` specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area. 

There are four available positions,

* `Bottom` - Sets the position of the navigation bar items to the bottom.
* `Left` - Sets the position of the navigation bar items to the left.
* `Top` - Sets the position of the navigation bar items to the top.
* `Right` - Sets the position of the navigation bar items to the right.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = NavigationStripPosition.Bottom;

{% endhighlight %}

{% endtabs %}

![](images/tabstrip.png)