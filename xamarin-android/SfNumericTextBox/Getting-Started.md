---
layout: post
title: Getting Started with Syncfusion® NumericTextBox control
description: A quick tour to initial users on Syncfusion® NumericTextBox (SfNumericTextBox) control for Xamarin.Android platform 
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---

# Getting Started with Xamarin.Android NumericTextBox (SfNumericTextBox)

This section explains you the steps to configure a SfNumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in SfNumericTextBox control.

## Reference Essential Studio<sup>®</sup> components in your solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfNumericTextBox.Android.dll

## Add SfNumericTextBox

* Adding reference to NumericTextBox.

{% capture codesnippet1 %}
 
{% tabs %}

{% highlight c# %}

using Com.Syncfusion.NumericTextBox; 

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

* Create an instance of SfNumericTextBox.

{% capture codesnippet2 %}
 
{% tabs %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox(this);
SetContentView(numericTextBox);

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }}

## Set Value

The SfNumericTextBox control display value can be set using `Value` property.

{% tabs %}

{% highlight c# %}

numericTextBox.Value = 123.45;

{% endhighlight %}

{% endtabs %}


## Enable Parsing Mode

The value of the SfNumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% tabs %}

{% highlight c# %}

numericTextBox.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

{% endtabs %}

## Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% tabs %}

{% highlight c# %}

	numericTextBox.FormatString = "c";

{% endhighlight %}

{% endtabs %}

![Xamarin.Android NumericTextBox](images/gettingstarted.png) 