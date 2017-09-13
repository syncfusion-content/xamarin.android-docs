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

    
	using Com.Syncfusion.Gauges.SfCircularGauge;


	  protected override void OnCreate(Bundle bundle)
		 {
			base.OnCreate(bundle);
			SfCircularGauge circularGauge = new SfCircularGauge(this);
			// Set our view from the "main" layout resource
			SetContentView(circularGauge);
		 }
    
{% endhighlight %}

![](getting-started_images/getting-started_img2.png)

## Adding Header

You can assign a unique header to `SfCircularGauge` by making use of `Header` property and you can positioned it wherever you want using `Position` property.


{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge(this);
    Header header = new Header();
    header.Text = "Speedometer";
    header.TextSize = 20;
    header.Position = new PointF((float)0.5, (float)0.7);
    header.TextColor = Color.Gray;
    circularGauge.Headers.Add(header); 
    SetContentView(circularGauge);

{% endhighlight %}

## Configuring Scales

You can configure the `CircularScale` elements by making use of following API's available in SfCircularGage.

They are:

* StartAngle
* SweepAngle
* StartValue
* EndValue
* Interval
* RimThickness
* RimColor

{% highlight c# %}

     ObservableCollection<CircularScale> circularScales = new ObservableCollection<CircularScale>();
         CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.Interval = 10;
            scale.StartAngle = 135;
            scale.SweepAngle = 270;
            scale.RimWidth = 10;
            scale.RimColor = Color.Gray;
            scale.MinorTicksPerInterval = 0;
            circularScales.Add(scale);
            circularGauge.CircularScales = circularScales;
        circularGauge.CircularScales = circularScales;
        SetContentView(circularGauge);

{% endhighlight %}

## Adding Ranges

You can add ranges to SfCircularGauge by creating ranges collection using `Ranges`.

{% highlight c# %}

    ...
    CircularRange range = new CircularRange();
    range.StartValue = 0;
    range.EndValue = 80;
    range.Color = Color.ParseColor("#2bbfb8");
    range.Width = 10;
    circularRanges.Add(range);
    scale.CircularRanges = circularRanges;
    circularGauge.CircularScales = circularScales;
    SetContentView(circularGauge);

{% endhighlight %}

## Adding a Needle Pointer

You can create a needle pointer and associate it with a scale to display the current value.

{% highlight c# %}

    List<CircularPointer> pointers = new List<CircularPointer>();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 60;
    needlePointer.Color = Color.White;
    needlePointer.KnobColor = Color.White;
    needlePointer.Width = 5;
    needlePointer.KnobRadius = 20;
    needlePointer.LengthFactor = 0.8;
    pointers.Add(needlePointer);
    scale.CircularPointers = pointers;
    circularScales.Add(scale);
    circularGauge.CircularScales = circularScales;
   

{% endhighlight %}

## Adding a Range Pointer

A range pointer provides an alternative way of indicating the current value.

{% highlight c# %}

     List<CircularPointer> pointers = new List<CircularPointer>();
            RangePointer rangePointer = new RangePointer();
            rangePointer.Value = 70;
            rangePointer.Color = Color.ParseColor("#2bbfb8");
            rangePointer.Width = 10;
            pointers.Add(rangePointer);
            scale.CircularPointers = pointers;
            circularScales.Add(scale);
            circularGauge.CircularScales = circularScales;

{% endhighlight %}

![](getting-started_images/getting-started_img3.png)
