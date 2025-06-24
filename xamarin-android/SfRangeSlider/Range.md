---
layout: post
title: Range in Syncfusion® RangeSlider Control for Xamarin.Android
description: Learn how to set dual thumb slider and configure ranges in RangeSlider control.
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# Range

The SfRangeSlider control supports selecting a range of values by using two thumbs, providing flexibility for scenarios where you need to define both minimum and maximum boundaries within a dataset.

## Enable Range Mode

The `ShowRange` property controls whether the slider operates in single-thumb or dual-thumb mode. Set this property to `true` to display two thumbs on the track for range selection.

N> When this property is set to `false`, a single thumb is displayed for selecting individual values without range functionality.

{% tabs %}

{% highlight c# %}

	rangeSlider.ShowRange= True;

{% endhighlight %}

{% endtabs %}

## Configure Range Values

Range values can be customized using the `RangeStart` and `RangeEnd` properties to define the initial selected range when the control loads.
### RangeStart

Gets and sets the start value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeStart=0;

{% endhighlight %}

{% endtabs %}

### RangeEnd

Gets and sets the end value of the range.

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeEnd=10;

{% endhighlight  %}

{% endtabs %}

## ValueChangeMode

The ValueChangeMode property changes the value based on the touch of the `SfRangeSlider` control. It consists of the following two types

* Default
* OnThumbPress

N> The default value of the ValueChangeMode property is `Default`.


### Default

The value is updated when you touch inside the control.

{% tabs %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.Default;

{% endhighlight %}

{% endtabs %}


### OnThumb

The value is updated when you touch or move the thumb/knob.

{% tabs %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.OnThumb;

{% endhighlight %}

{% endtabs %}

## Value
Gets or sets the range value, which ranges between Minimum and Maximum. The default value of RangeSlider is 0.

{% tabs %}

{% highlight c# %}

	 rangeSlider.Value = 30;

{% endhighlight %}

{% endtabs %}
