---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.Android
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.Android platform
platform: Xamarin.Android
control: LinearGauge
documentation: ug
---

# Getting Started

This section explains how to create the SfLinearGauge and configure its properties. It walks through the entire process of creating a SfLinearGauge for Xamarin.Android.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfLinearGauge.Android.dll

## Add SfLinearGauge

The SfLinearGauge control is configured entirely in C# code. The following steps explain on how to create a SfLinearGauge and configure its elements.

* Adding namespace for the added assemblies.

{% tabs %}

{% highlight c# %}

using Com.Syncfusion.LinearGauge; 

{% endhighlight %}

{% endtabs %}

* Now add the SfLinearGauge control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

SfLinearGauge linearGauge = new SfLinearGauge (this);
SetContentView(linearGauge);
	
{% endhighlight %}

{% endtabs %}

* Configure the properties of SfLinearGauge

{% tabs %}

{% highlight c# %}

linearGauge.SetOrientation (SfLinearGauge.Orientation.Vertical);

{% endhighlight %}

{% endtabs %}

## Add Scales

The scale that point out to the values can be added by instantiating LinearScale class and setting minimum values, maximum values, scale intervals and colors etc.

{% tabs %}

{% highlight c# %}

ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale> ();
LinearScale outerScale = new LinearScale ();
outerScale.Minimum = 0;
outerScale.Maximum = 100;
outerScale.ScaleBarSize = 50;
outerScale.ScaleBarLength = 100;
outerScale.Interval = 20;
outerScale.ScaleBarColor = Color.ParseColor ("#FAECEC");
outerScale.MinorTicksPerInterval = 2;
outerScale.LabelFontSize = 17;
outerScale.LabelColor = Color.ParseColor ("#545454");
outerScale.LabelPostfix = "%";
			
{% endhighlight %}

{% endtabs %}

Before adding scales to Array list, Add range value to Scale.

## Add Symbol Pointer

An arrow head that points to the value is called the Symbol Pointer which can be added by instantiating the SymbolPointer class and assigning it to the Pointers collection.

{% tabs %}

{% highlight c# %}

ObservableCollection<LinearPointer> pointers = new ObservableCollection<LinearPointer> ();
SymbolPointer outerScale_needlePointer = new SymbolPointer ();
outerScale_needlePointer.Value = pointervalue;
outerScale_needlePointer.StrokeWidth = 0;
outerScale_needlePointer.Offset = 0.3f;
outerScale_needlePointer.Color = Color.ParseColor ("#414D4F");
pointers.Add (outerScale_needlePointer);
			
{% endhighlight %}

{% endtabs %}

## Add a Bar Pointer

A flat solid bar that points to the current value can be added by instantiating BarPointer and it can be added to pointers collection.

{% tabs %}

{% highlight c# %}
		
BarPointer rangePointer = new BarPointer ();
rangePointer.Value = barvalue;
rangePointer.Color = Color.ParseColor ("#CE4545");
rangePointer.StrokeWidth = 20;
pointers.Add (rangePointer);
outerScale.Pointers = pointers;
			
{% endhighlight %}

{% endtabs %}

## Add a Range

We can improve the readability of data by including ranges that quickly display when values fall within specific ranges.

{% tabs %}

{% highlight c# %}

ObservableCollection<LinearRange> ranges = new ObservableCollection<LinearRange> ();
LinearRange lowerRange = new LinearRange ();
lowerRange.StartWidth = 30;
lowerRange.EndWidth = 30;
lowerRange.Color = Color.ParseColor ("#67d6db");
lowerRange.StartValue = 0;
lowerRange.EndValue = 50;
lowerRange.Offset = -0.3;
ranges.Add (lowerRange);

LinearRange higherRange = new LinearRange ();
higherRange.StartWidth = 30;
higherRange.EndWidth = 30;
higherRange.Color = Color.ParseColor ("#32B8C6");
higherRange.StartValue = 50;
higherRange.EndValue = 100;
higherRange.Offset = -0.3;
ranges.Add (higherRange);

outerScale.Ranges = ranges;
scales.Add (outerScale);
linearGauge.Scales = scales;
			
{% endhighlight %}

{% endtabs %}

![](images/Studio.png)



