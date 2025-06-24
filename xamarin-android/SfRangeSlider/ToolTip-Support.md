---
layout: post
title: Tooltip Support for Syncfusion® RangeSlider Control for Xamarin.Android
description: Learn how to configure and customize tooltips for RangeSlider in Xamarin.Android
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# Tooltip Support

The tooltip displays the current value based on the thumb position, providing immediate visual feedback to users during slider interaction. This feature enhances user experience by showing precise values without requiring additional UI elements.
## Set Tooltip Precision

The `ToolTipPrecision` property defines the number of decimal places displayed in the tooltip value. This is particularly useful when working with precise decimal values or when you need to control the level of detail shown to users.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the Tooltip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options.

1. BottomRight
2. TopLeft
3. None

### BottomRight

The Tooltip will be placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

The Tooltip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

Tooltip will be collapsed.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}

{% endtabs %}

## Tooltip color

`TooltipTextColor` - Used to change the tooltip text color.
`TooltipBackgroundColor` - Used to change the tooltip background color.


