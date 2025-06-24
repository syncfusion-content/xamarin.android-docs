---
layout: post
title: Auto Reverse Feature in Syncfusion® NumericUpDown Control for Xamarin.Android
description: Learn how to enable auto reverse functionality, set value ranges, and configure step values in the SfNumericUpDown control for Xamarin.Android.
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
keywords: NumericUpDown, auto reverse, minimum, maximum, step value, range, continuous spinning
---
# Auto Reverse

The Auto Reverse feature allows the `SfNumericUpDown` control to automatically cycle between minimum and maximum values. When incrementing, the control will start from the minimum value once it reaches the maximum value, and vice versa when decrementing.
N> By default, the `AutoReverse` property value is `false`.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

numericupdown.AutoReverse = true;

{% endhighlight %}

{% endtabs %}

## Continuous Spinning Between Ranges

You can restrict the values between a specific range by setting the `Maximum` and `Minimum` property values. When auto reverse is enabled, the control will continuously cycle within this defined range.
N> By default, the `Minimum` property value is `0` and the `Maximum` property value is `100`.

N> By default the minimum property value is 0 and maximum property value is 100.

{% tabs %}

{% highlight C# %}

sfNumericUpDown.Minimum = 10;
sfNumericUpDown.Maximum = 50

{% endhighlight %}

{% endtabs %}

![Maximum Value](images/maximum.png)

![Minimum Value](images/minimum.png)

## Set Increment Step

The frequency at which values are incremented or decremented can be configured using the `StepValue` property. This determines how much the value changes with each increment or decrement operation.
N> By default, the `StepValue` property value is `1`.

N> By default the property value is 1.

{% tabs %}

{% highlight C# %}

	sfNumericUpDown.StepValue = 6;

{% endhighlight %}

{% endtabs %}
