---
layout: post
title: Set Maximum Decimal Digits in Syncfusion® NumericUpDown for Xamarin.Android
description: Learn how to configure the maximum number of decimal digits to be displayed in the NumericUpDown control.
platform: xamarin.android
control: NumericUpDown
documentation: ug
keywords: NumericUpDown, decimal digits, precision, number formatting, decimal places
---
# Set Maximum Number of Decimal Digits

The `SfNumericUpDown` control allows you to specify the maximum number of digits to be displayed after the decimal point using the `MaximumNumberDecimalDigits` property. This feature is useful for controlling the precision of numeric values and ensuring consistent formatting across your application.

N> The `MaximumNumberDecimalDigits` property accepts positive values only. The default value is determined by the current culture settings.

## Basic Usage
{% tabs %}

{% highlight C# %}

numeric.MaximumNumberDecimalDigits = 2;

{% endhighlight %}

{% endtabs %}
