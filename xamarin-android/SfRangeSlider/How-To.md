---
layout: post
title: Events in Syncfusion® RangeSlider control for Xamarin.Android
description: Learn how to populate events in RangeSlider control
platform: Xamarin.Android
control: RangeSlider 
documentation: ug
---

## How to get notifications when a thumb drag is started and completed?

The `DragStarted` event is raised when a thumb is dragged. After the thumb releases the pointer capture, the `DragCompleted` event is raised. The `IsStartThumb` property of the `DragThumbEventArgs` returns a boolean value, which indicates the thumb used for performing drag operations.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>IsStartThumb</td>
<td>Indicates the thumb used for performing drag operations.</td>
</tr>
</table>

                                                
{% highlight c# %}

	rangeSlider.DragStarted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

	rangeSlider.DragCompleted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

{% endhighlight %}

## How to trigger ValueChanged event?

The `ValueChanged` event is triggered when `SfRangeSlider` value is changed. The argument contains the value of RangeSlider.

`Value` - Used to gets or sets the value for range slider.

{% highlight c# %}

        private void RangeSlider_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            var rangeValue = e.Value;
        }

{% endhighlight %}

## How to trigger RangeChanged event?

The `RangeChanged` event is triggered when either RangeStart or RangeEnd values are changed. The argument contains the following information.

`RangeStart` – Gets or sets the range start value of range slider.
`RangeEnd` – Gets or sets the range end value of range slider.

{% highlight c# %}

        private void RangeSlider_RangeChanged(object sender, RangeChangedEventArgs e)
        {
            var rangeStart = e.RangeStart;
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

## How to trigger RangeStartChanged event?

The `RangeStartChanged` event is triggered when `RangeStart` value is changed. The argument contains `RangeStart` value.

{% highlight c# %}

        private void RangeSlider_RangeStartChanged(object sender, RangeStartChangedEventArgs e)
        {
            var rangeStart = e.RangeStart;
        }

{% endhighlight %}

## How to trigger RangeEndChanged event?

The `RangeEndChanged` event is triggered when `RangeEnd` value is changed. The argument contains `RangeEnd` value.

{% highlight c# %}

        private void RangeSlider_RangeEndChanged(object sender, RangeEndChangedEventArgs e)
        {
            var rangeEnd = e.RangeEnd;
        }

{% endhighlight %}

## How to trigger ThumbTouchDown event?

The `ThumbTouchDown` event occurs when touching the thumb. The argument contains the state of the thumb.

`IsStartThumb` - Gets the state whether thumb touch down position is start or end. If the thumb touch down position is start, then `IsStartThumb` state is true. If it's end, then `IsStartThumb` state is false. It is a read only property.

{% highlight c# %}

        private void RangeSlider_ThumbTouchDown(object sender, DragThumbEventArgs e)
        {
          var isStartThumb=  e.IsStartThumb;
        }

{% endhighlight %}

## How to trigger ThumbTouchUp event?

`IsStartThumb` - Gets the state whether thumb touch up position is start or end. If the thumb touch up position is start, then `IsStartThumb` state is true. If it's end, then IsStartThumb state is false. It is a read only property.

{% highlight c# %}

        private void RangeSlider_ThumbTouchUp(object sender, DragThumbEventArgs e)
        {
            var isStartThumb = e.IsStartThumb;
        }

{% endhighlight %}

