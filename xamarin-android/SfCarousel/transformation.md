---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Android
description : Learn how to set the Transformation in Carousel for Xamarin.Android
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# Transformation

## Rotation Angle

The `RotationAngle` property in the SfCarousel control is used to rotate all the items in a specified angle. 

If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

N> This angle can also be specified from 0 to 360.

{% highlight C# %}

	carousel.RotationAngle=40;

{% endhighlight %}

![](images/rotationangle.png)

## Offset

### Items Offset

Specify the distance between the items in SfCarousel panel using `Offset` property.

N> The default value is 20.

{% highlight C# %}

	carousel.Offset=30;

{% endhighlight %}

![](images/offset.png)

### Selected Item Offset

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property.

N> The default value is 0.

{% highlight C# %}

	carousel.SelectedItemOffset=5;

{% endhighlight %}

### Scale Offset

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% highlight C# %}
	
	carousel.ScaleOffset=0.7f;

{% endhighlight %}

![](images/scaleoffset.png)

