---
layout: post
title: Transformation in Syncfusion® Carousel control in Xamarin.Android
description: Learn how to implement Transformation settings in Carousel control for Xamarin.Android and customize advanced visual effects and transitions.
platform: xamarin.android
control: SfCarousel
documentation: ug
---

# Transformation

## Tilt Non-Selected Items

The `RotationAngle` property in the SfCarousel control is used to rotate all items to a specified angle.

If the angle value is positive, the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction.

N> This angle can be specified from 0 to 360 degrees.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.RotationAngle=40;

{% endhighlight %}

![Rotation angle transformation](images/rotationangle.png)

## Set Gap between Unselected Items

Specify the distance between items in the SfCarousel panel using the `Offset` property.

N> The default value is 20.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.Offset=30;

{% endhighlight %}

![Offset between items](images/offset.png)

## Set Gap between Selected Item and Unselected Items

The distance between the selected item and other items can be customized using the `SelectedItemOffset` property.

N> The default value is 0.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.SelectedItemOffset=5;

{% endhighlight %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all unselected items to the specified scale value.

{% highlight C# %}
	
SfCarousel carousel = new SfCarousel(this);
carousel.ScaleOffset=0.7f;

{% endhighlight %}

![Scale offset transformation](images/scaleoffset.png)

## Spacing between Items in Linear Mode

The spacing of all items in Linear mode can be determined using the `ItemSpacing` property.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ItemSpacing=5;
carousel.ViewMode=ViewMode.Linear;

{% endhighlight %}
