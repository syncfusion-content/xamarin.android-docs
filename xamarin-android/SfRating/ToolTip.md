---

layout: post
title: Tooltip in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the toolTip of rating control
platform: Xamarin.Android
control: Rating
documentation: ug

---

# ToolTip

A ToolTip is a short description view that is used to understand the unfamiliar object that aren't directly displayed in the UI. In Xamarin.Forms SfRating control TooTip shows the dat's of `Value`. It will be displayed when we move cursor over the rating items. It will be disappered when we select rating item.

## Set Tooltip Placement

Using `ToolTipPlacement` property, We can define where the ToolTip need to be displayed. TooTipPlacement having the folowing three types of placemnt.

*BottomRight,
*None,
*TopLeft.

N> By default, this property value is set to None.

### BottomRight

The Tooltip will display on bottom of the rating stars. 

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![](images/rightBottom.jpg)

### TopLeft 

The Tooltip will display on top of the rating stars. 

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![](images/leftTop.jpg) 

### None

When we set ToolTipPlacemnt as None, The ToolTip will be disappear.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.None;

{% endhighlight %}

{% endtabs %}

![](images/null.jpg)

## Set ToolTip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in Tooltip. 

N> The default value of ToolTip precision is 1. 

{% tabs %}

{% highlight C# %}

       rating.TooltipPrecision = 6;

{% endhighlight %}

{% endtabs %}

![](images/toolTipPrecision.jpg)