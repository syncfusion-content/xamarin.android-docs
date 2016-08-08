---
layout: post
title: Range in Syncfusion RangeSlider control for Xamarin.Android
description: Learn how to set Dual thumb slider and its ranges in RangeSlider control.
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# Range

The SfRangeSlider control supports to select range of value by using two Thumbs.

## Set Show Range

The `ShowRange` property should be set to true for displaying two thumbs in track with range of values.

N> When this property is set to false, single thumb is displayed without any range 

{% tabs %}

{% highlight c# %}

	rangeSlider.ShowRange= True;

{% endhighlight %}

{% endtabs %}

## Set Range values

Ranges can be customized using RangeStart and RangeEnd properties in SfRangeSlider.

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
