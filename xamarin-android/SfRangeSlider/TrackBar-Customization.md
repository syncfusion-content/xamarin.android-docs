---
layout: post
title: TrackBar Customization in Syncfusion® RangeSlider Control for Xamarin.Android
description: Learn how to customize the track bar appearance, colors, and styling of RangeSlider control in Xamarin.Android
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# TrackBar Customization

## TrackStroke

The `TrackStroke` property controls the width of the entire track bar, affecting the visual prominence and touch target size of the slider.

{% tabs %}

{% highlight c# %}

	rangeSlider.TrackStroke = 5;

{% endhighlight %}

{% endtabs %}

## TrackSelectionStroke

 The `TrackSelectionStroke` property customizes the stroke width for the selected range or selected portion of the track bar, providing visual distinction between selected and unselected areas.
{% tabs %}

{% highlight c# %}

	rangeSlider.TrackSelectionStroke = 5;

{% endhighlight %}

{% endtabs %}

## TrackColor

The `TrackColor` property customizes the color of the entire track bar background, establishing the base visual appearance of the slider.

{% tabs %}

{% highlight c# %}

	 rangeSlider.TrackColor = Color.Red;

{% endhighlight %}

{% endtabs %}

## TrackSelectionColor

The `TrackSelectionColor` property customizes the color for the selected range or selected portion of the track bar, providing clear visual feedback about the current selection.

{% tabs %}

{% highlight c# %}

	 rangeSlider.TrackSelectionColor = Color.Red;

{% endhighlight %}

{% endtabs %}

## KnobColor

The `KnobColor` property changes the color of the thumb (knob) that users interact with to adjust values.
{% tabs %}

{% highlight c# %}

    rangeSlider.KnobColor = Color.Orange;

{% endhighlight %}

{% endtabs %}

## ThumbSize

The `ThumbSize` property controls the size of the thumb, affecting both visual appearance and touch interaction area.

{% tabs %}

{% highlight c# %}

    rangeSlider.ThumbSize = 5;

{% endhighlight %}

{% endtabs %}
