---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.Android
description: A quick tour to initial users on Syncfusion numericTextBox control for Xamarin.Android platform 
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---

# Getting Started

This section explains you the steps to configure a NumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in NumericTextBox control.

![](images/gettingstarted.png) 

## Creating your first NumericTextBox in Xamarin.Android

### Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfNumericTextBox.Andriod.dll

### Add and configure the NumericTextBox

* Adding reference to numerictextbox.

{% highlight c# %}

	using Com.Syncfusion.NumericTextBox; 

{% endhighlight %}

* Create an instance of SfNumericTextBox.

{% highlight c# %}

	SfNumericTextBox sfNumericTextBox=new SfNumericTextBox(this);
	SetContentView(sfNumericTextBox);

{% endhighlight %}


### Setting Value

The NumericTextBox control display value can be set using `Value` property.

{% highlight c# %}

	sfNumericTextBox.Value = 123.45;

{% endhighlight %}


### Enable Parsing Mode

The value of the NumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% highlight c# %}

	sfNumericTextBox.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}


### Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% highlight c# %}

	sfNumericTextBox.FormatString = "c";

{% endhighlight %}

