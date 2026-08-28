---

layout: post
title: Tooltip in Syncfusion® Rating Control for Xamarin.Android
description: Learn here all about Tooltip support in Syncfusion® Xamarin.Android Rating (SfRating) control, its elements and more.
platform: xamarin.android
control: Rating
documentation: ug

---

# Tooltip in Rating (SfRating)

Tooltips provide additional information about objects that are unfamiliar to users and are not directly displayed in the UI. In the Xamarin.Android SfRating control, the tooltip displays the current `Value` of the rating. It appears when users interact with the rating items and disappears when a rating item is selected or when the interaction ends.

## Set Tooltip Placement

Using the `ToolTipPlacement` property, you can define where the tooltip should be displayed. The `ToolTipPlacement` property supports the following three options:

* **BottomRight** - Displays tooltip at the bottom-right of the rating control
* **None** - Disables tooltip display
* **TopLeft** - Displays tooltip at the top-left of the rating control
N> By default, the value of the `ToolTipPlacement` property is set to `None`.

### TopLeft Placement

The tooltip will be displayed at the top-left position relative to the rating stars.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Tooltip at Top-Left Position](images/leftTop.jpg)

### BottomRight Placement

The tooltip will be displayed at the bottom-right position relative to the rating stars.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![Tooltip at bottom](images/rightBottom.jpg)

### None

The tooltip will be disappeared when setting ToolTipPlacement to None.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.None;

{% endhighlight %}

{% endtabs %}

![No Tooltip Display](images/null.jpg)

## Set Tooltip Precision

The `ToolTipPrecision` property controls the number of decimal places displayed in the tooltip value. This is particularly useful when working with precise rating values.
N> The default value of this property is 1. 

{% tabs %}

{% highlight C# %}

       rating.TooltipPrecision = 6;

{% endhighlight %}

{% endtabs %}

![Tooltip Precision](images/toolTipPrecision.jpg)

