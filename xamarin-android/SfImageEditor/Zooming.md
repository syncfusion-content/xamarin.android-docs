---
layout : post
title : Zooming and Panning in Syncfusion SfImageEditor control in Xamarin.Android
description : Learn how to perform Zooming and panning image in ImageEditor for Xamarin.Android
platform : xamarin.android
control : ImageEditor
documentation : ug
---

## Zooming

The image editor control provides support for zooming and panning.You can Zoom in and Zoom out image  in image editor control.

The following properties are related to the zooming feature of the image editor control:

* EnableZooming
* Maximum ZoomLevel

## EnableZooming

 You can Enable or Disable zooming by setting Enable Zooming to either true or false.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;

{% endhighlight %}

{% endtabs %}

## Maximum ZoomLevel

You can customize maximum zoom level  by setting value to Maximum ZoomLevel property in image editor control.

{% tabs %}

{% highlight C# %}

     editor.EnableZooming = true;
     editor.MaximumZoomLevel = 8;

{% endhighlight %}

{% endtabs %}

## PanningMode

Image editor control provides support for panning. Image editor allows you to pan the image with two fingers or single finger by setting the PanningMode in image editor.

The following properties are used in the panning.

* Single Finger – You can zoom or pan the image but it restrict the select or move the shapes.

* Two Finger – You can zoom or pan the image and also select or move the shapes.

By default, PanningMode value as TwoFinger.

{% tabs %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/zoom.png)


