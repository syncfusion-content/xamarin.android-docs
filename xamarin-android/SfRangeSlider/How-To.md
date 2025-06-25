---
layout: post
title: Events in Syncfusion® RangeSlider Control for Xamarin.Android
description:  Learn how to handle events in RangeSlider control for responsive user interactions and implement custom behaviors in Xamarin.Android applications.
platform: xamarin.android
control: RangeSlider 
documentation: ug
---
# Events in Syncfusion® RangeSlider Control for Xamarin.Android
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

## Value Change Events

### How to Handle ValueChanged Event

The `ValueChanged` event is triggered when the SfRangeSlider value changes in single thumb mode. This event is useful for responding to value changes in real-time.

**Event Arguments:**
- `Value` - Gets the current value of the range slider
{% highlight c# %}

        private void RangeSlider_ValueChanged(object sender, ValueChangedEventArgs e)
        {
            var rangeValue = e.Value;
        }

{% endhighlight %}

### How to Handle RangeChanged Event

The `RangeChanged` event is triggered when either `RangeStart` or `RangeEnd` values change in double thumb mode. This event provides both range values simultaneously.

**Event Arguments:**
- `RangeStart` - Gets the range start value of the range slider
- `RangeEnd` - Gets the range end value of the range slider
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

