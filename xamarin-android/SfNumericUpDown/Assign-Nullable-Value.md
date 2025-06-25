---
layout: post
title: Assign Nullable Value in Syncfusion® NumericUpDown for Xamarin.Android
description: Learn how to assign nullable values and configure watermark text in the SfNumericUpDown control for Xamarin.Android.
platform: xamarin.android
control: NumericUpDown
documentation: ug
keywords: NumericUpDown, nullable value, watermark, hint text, AllowNull
---
# Assign Nullable Value

The `SfNumericUpDown` control supports nullable values, allowing you to set null values in the `Value` property by setting the `AllowNull` property to `true`.
N> By default, the `AllowNull` property value is `false`.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

	numericupdown.AllowNull=true;

{% endhighlight %}

{% endtabs %}

![Nullable Value Support](images/allownull.png)

## Set Hint Text

The `Watermark` property can be used to provide a hint that helps users get started with their input. The watermark text is visible when the value is empty or null.

{% tabs %}

{% highlight C# %}

	numericupdown.Watermark = "Numeric Text";
	
{% endhighlight %}

{% endtabs %}

![Watermark Text](images/watermark.png)
