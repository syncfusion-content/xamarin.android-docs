---
layout: post
title: Decimal Digits in Syncfusion® NumericTextBox Control for Xamarin.Android
description: Learn how to set maximum decimal digits and control default decimal digits support in Xamarin.Android NumericTextBox.
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---
# Decimal Digits in NumericTextBox Control

## Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Numerictextbox.SfNumericTextBox.html#Com_Syncfusion_Numerictextbox_SfNumericTextBox_MaximumNumberDecimalDigits) property. 

N> The `MaximumNumberDecimalDigits` property can be provided with a positive value only.

{% tabs %}

{% highlight c# %}

	numericTextBox.MaximumNumberDecimalDigits=2;
  
{% endhighlight %}

{% endtabs %}

![Display the NumericTextBox value with maximum decimal digits](images/MaximumNumberDecimalDigits.png)

## Remove Default Decimal Digits in Xamarin NumericTextBox

Based on the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Numerictextbox.SfNumericTextBox.html#Com_Syncfusion_Numerictextbox_SfNumericTextBox_MaximumNumberDecimalDigits) property, the default number of decimal digits is displayed. By disabling the `AllowDefaultDecimalDigits` Boolean property, those default digits can be removed from the NumericTextBox view.

{% tabs %}

{% highlight c# %}
            
    numericTextBox.AllowDefaultDecimalDigits = false;
  
{% endhighlight %}

{% endtabs %}

![Display the NumericTextBox value without default decimal digits](images/AllowDefaultDecimalDigits.png)
