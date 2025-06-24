---
layout: post
title: Range Support in Syncfusion® NumericTextBox Control for Xamarin.Android
description: Learn how to use range support to restrict input values within specified minimum and maximum limits in NumericTextBox control.
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---

# Range Support

You can restrict the values within a specific range by setting the `Maximum` and `Minimum` property values.

{% tabs %}
	
{% highlight c# %}
	
        SfNumericTextBox numericTextBox = new SfNumericTextBox(this);
        numericTextBox.Minimum = 50;
        numericTextBox.Maximum = 1000;
        numericTextBox.Value = 10;
        SetContentView(numericTextBox);
			
{% endhighlight %}

{% endtabs %}

N> Default Value of `Maximum` and `Minimum` is "null".