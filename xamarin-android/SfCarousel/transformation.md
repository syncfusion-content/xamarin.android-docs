---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Android
description : Learn how to set the Transformation in Carousel for Xamarin.Android
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# Transformation

The Offset between selected and unselected item can be customized in SfCarousel control. And also the items can be scaled to the specified value.

## Tilt Non Selected Items

The `RotationAngle` property in the SfCarousel control is used to rotate all the items in a specified angle. 

If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

N> This angle can also be specified from 0 to 360.

{% tabs %}

{% highlight C# %}

carousel.RotationAngle=40;

{% endhighlight %}

{% endtabs %}

![](images/rotationangle.png)

## Set Gap between Unselected Items

Specify the distance between the items in SfCarousel panel using `Offset` property.

N> The default value is 20.

{% tabs %}

{% highlight C# %}

carousel.Offset=30;

{% endhighlight %}

{% endtabs %}

![](images/offset.png)

## Set Gap between Selected Item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property.

N> The default value is 0.

{% tabs %}

{% highlight C# %}

carousel.SelectedItemOffset=5;

{% endhighlight %}

{% endtabs %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% tabs %}

{% highlight C# %}
	
	carousel.ScaleOffset=0.7f;

{% endhighlight %}

{% endtabs %}

![](images/scaleoffset.png)

