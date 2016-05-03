---
layout: post
title: Pointers of LinearGauge in Xamarin.Android
description: Learn how to define pointers in LinearGauge
platform: Xamarin.Android
control: LinearGauge
documentation: ug
---

# Pointers

## BarPointer

Barpointer is an accenting line or colored bar that is placed on the Linear Gauge to mark the values. 

{% highlight c# %}

	List<LinearPointer> pointers = new List<LinearPointer> ();
    BarPointer rangePointer = new BarPointer ();
	rangePointer.Value = 50;
	rangePointer.Color = Color.FromRgb (206, 69, 69);
	rangePointer.Thickness = 10;
	pointers.Add (rangePointer);

{% endhighlight %}

![](images/BarPointer.png)

## SymbolPointer

In SymbolPointer, the value is pointed by a symbol on the scale. The Symbol Pointer class is derived from Pointer class. You can modify the symbol pointer’s size using the StrokeWidth property. The color of the symbol pointer is changed using the Color property.

{% highlight c# %}

	List<LinearPointer> pointers = new List<LinearPointer> ();
    //SymbolPointer
	SymbolPointer symbolPointer = new SymbolPointer ();
	symbolPointer.Value = 50;
	symbolPointer.Offset = 0.0;
	symbolPointer.Thickness = 3;
	symbolPointer.Color = Color.FromRgb (65, 77, 79);
	pointers.Add (symbolPointer);

{% endhighlight %}

![](images/SymbolPointer.png)