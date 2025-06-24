---
layout: post
title: Set header to the Syncfusion® BusyIndicator control for Xamarin.Android
description: Learn how to set header text and customize font properties for the BusyIndicator control
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Set Header

The SfBusyIndicator control provides an option to display informative text that indicates the current loading status. You can set this header text using the `Title` property to provide users with context about the ongoing operation.
{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType = AnimationTypes.Battery;
	busyIndicator.Title="Loading...";
	
{% endhighlight %}

{% endtabs %}

![](images/Title_img1.png) 
                                          
BusyIndicator with header text
{:.caption}

## FontFace

You can customize the font style and size of the header text that appears beneath the animation. Use the `FontFace` property to modify the typography settings and enhance the visual appearance of your loading indicator.
{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.Battery;
	busyIndicator.Title="Loading...";
	busyIndicator.Fontface=Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

{% endtabs %}

![](images/Title_img2.png)   
                                                  
BusyIndicator with custom font face
{:.caption}


