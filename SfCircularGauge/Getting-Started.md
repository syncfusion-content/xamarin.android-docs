---

layout: post
title: Syncfusion SfCircularGauge control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion SfCircularGauge control for Xamarin.Android  Platform
platform: Xamarin.Android
control: SfCircularGauge
documentation: ug

---


# Getting Started

## Create your first Circular Gauge in Xamarin.Android Studio

You can configure an Xamarin.Android Circular Gauge in simple steps. In this section, you can learn how to configure a Circular Gauge control in a real-time scenario and also provides a walk-through on some of the customization features available in Circular Gauge control.

## Initialize the Circular Gauge

Create a Circular Gauge instance in Main Page and set Circular Gauge as a ContentView in onCreate() overridden method.


{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge ();
    this.Content = circulargauge;
    
{% endhighlight %}

![](getting-started_images/getting-started_img2.png)

## Adding Header

You can assign a unique header to **SfCircularGauge** by making use of **Header** property and you can positioned it wherever you want using **Position** property.


{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    Header header = new Header();
    header.Text = "Speedmeter";
    header.TextSize = 20;
    header.Position = Device.OnPlatform(iOS: new Point(.3, .7), new Point(0.38, 0.7), WinPhone: new Point(0.38, 0.7));
    header.ForegroundColor = Color.Gray;
    circularGauge.Headers.Add(header); 
    this.content = circularGauge;

{% endhighlight %}

## Configuring Scales

You can configure the **CircularScale** elements by making use of following API’s available in SfCircularGage.

They are:

* StartAngle
* SweepAngle
* StartValue
* EndValue
* Interval
* RimThickness
* RimColor

{% highlight c# %}

    Scale scale = new Scale(); 
    scale.StartValue = 0; 
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness =  20;
    scale.RimColor = Color.FromHex("#d14646");
    scale.MinorTicksPerInterval = 0;
    circularGauge.Scales = scale;
    this.Content= circulargauge;

{% endhighlight %}

## Adding Ranges

You can add ranges to SfCircularGauge by creating ranges collection using **Ranges**.

{% highlight c# %}

    …
    Range range = new Range(); 
    range.StartValue = 0; 
    range.EndValue = 80; 
    range.Color = Color.FromHex("#FF777777"); 
    range.Thickness = 10;
    scale.Ranges.Add(range);
    circularGauge.Scales = scale; 
    this.Content= circulargauge;

{% endhighlight %}

## Adding a Needle Pointer

You can create a needle pointer and associate it with a scale to display the current value.

{% highlight c# %}

    …
    NeedlePointer needlePointer = new NeedlePointer(); 
    needlePointer.Value = 60; 
    needlePointer.Color = Color.White; 
    needlePointer.KnobColor = Color.White; 
    needlePointer.Thickness = 5;
    needlePointer.KnobRadius = 20;
    needlePointer.LengthFactor = 0.8;
    scale.Pointers.Add(needlePointer); 
    circularGauge.Scales = scale; 
    ...

{% endhighlight %}

## Adding a Range Pointer

A range pointer provides an alternative way of indicating the current value.

{% highlight c# %}

    ... 
    RangePointer rangePointer = new RangePointer();
    rangePointer.Value = 60; 
    rangePointer.Color = Color.FromHex("#2bbfb8");
    rangePointer.Thickness = 20; 
    scale.Pointers.Add(rangePointer);
    …

{% endhighlight %}

![](getting-started_images/getting-started_img3.png)
