---
layout: post
title: Selection Value Configuration in Syncfusion® RangeSlider for Android
description: Learn how to configure minimum value, maximum value, tick frequency, step frequency, and snapping behavior for RangeSlider
platform: xamarin.android
control: RangeSlider
documentation: ug
---

# Selection Value Configuration

The SfRangeSlider provides various customization options to configure selection values, boundaries, and snapping behavior to create precise and user-friendly range selection interfaces.
## Set Minimum Value

Gets or sets the minimum possible value of the range. The thumb could not move beyond that value.

{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum=0;

{% endhighlight %}

{% endtabs %}

## Set Maximum Value

Gets or sets the maximum possible value of the range. The thumb could not move after that value.

{% tabs %}

{% highlight c# %}

	rangeSlider.Maximum=24;

{% endhighlight %}

{% endtabs %}

## Configure Tick Frequency

The `TickFrequency` property is used to decide the number of ticks to be displayed along the track based on Minimum and Maximum values.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

{% endtabs %}

N> When the `SnapsTo` property is set to `Ticks`, the `TickFrequency` is used to specify the interval between snap points.

## Set Step Frequency

The `StepFrequency` property specifies the interval between step values, providing fine-grained control over value increments when snapping is enabled.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

{% endtabs %}

N> When the `SnapsTo` property is set to `StepValues`, the `StepFrequency` property is enabled.

## Set Snapping Mode

The `SnapsTo` property determines whether the RangeSlider snaps to steps or ticks. Available options for this property are

* `StepValues` - The `StepFrequency` property will be used to specify the interval between snap points.

* `Ticks` - The `TickFrequency` property will be used to specify the interval between snap points

* `None` - The thumb is moved independent of any values.

N> The default option is Ticks.

{% tabs %}

{% highlight c# %}

	rangeSlider.SnapsTo=SnapsTo.Ticks;

{% endhighlight %}

{% endtabs %}
