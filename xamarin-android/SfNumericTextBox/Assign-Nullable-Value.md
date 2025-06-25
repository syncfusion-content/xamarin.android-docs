---
layout: post
title: Syncfusion® NumericTextBox Nullable Value Support
description: Learn how to assign nullable values and set hint text in NumericTextBox control for Xamarin.Android.
platform: xamarin.android
control: NumericTextBox
documentation: ug
---
# Assign Nullable Value

Null values can be set in the SfNumericTextBox `Value` property by setting the `AllowNull` property value to `true`.

N> By default, the property value is `false`.

{% tabs %}

{% highlight c# %}

	numericTextBox.AllowNull=true;

{% endhighlight %}

{% endtabs %}

![NumericTextBox with AllowNull enabled](images/AllowNull.png)
## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user get started with their input. The watermark text is visible when the value is empty or null.

{% tabs %}

{% highlight c# %}

	numericTextBox.Watermark = "Principal Amount";
	
{% endhighlight %}

{% endtabs %}

![NumericTextBox with Watermark](images/WaterMark.png)
