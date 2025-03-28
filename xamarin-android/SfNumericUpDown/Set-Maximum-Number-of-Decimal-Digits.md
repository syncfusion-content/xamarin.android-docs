---
layout: post
title: Various Features in Syncfusion® NumericUpDown control for Xamarin.Android
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight C# %}

numeric.MaximumNumberDecimalDigits = 2;

{% endhighlight %}

{% endtabs %}