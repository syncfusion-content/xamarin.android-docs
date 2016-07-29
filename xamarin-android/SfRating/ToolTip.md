---

layout: post
title: Tooltip in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the toolTip of rating control
platform: Xamarin.Android
control: Rating
documentation: ug

---

# ToolTip

## Tooltip Placement

SfRating control provides Tooltip support with rating value using `TooltipPlacement` property. 

N> By default, this property value is set to None.

### TopLeft 

The Tooltip will display on top of the rating stars. 

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.TopLeft;

{% endhighlight %}

![](images/leftTop.jpg) 

### BottomRight

The Tooltip will display on bottom of the rating stars. 

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.BottomRight;

{% endhighlight %}

![](images/rightBottom.jpg)

### None

The Tooltip will be disabled.

{% highlight C# %}

	   rating.TooltipPlacement=TooltipPlacement.None;

{% endhighlight %}

![](images/null.jpg)

## Tooltip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in Tooltip. 

N> The default value of ToolTip precision is 1. 

{% highlight C# %}

       rating.TooltipPlacement=6;

{% endhighlight %}

![](images/toolTipPrecision.jpg)

