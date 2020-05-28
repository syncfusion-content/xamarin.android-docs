---
layout: post
title: selection indicator in Syncfusion SegmentedControl for Xamarin.Android
description: Learn how to handle selection indicator settings, selection text color and selection strip in Segmented control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Indicating the selected item

The segmented control indicates the selected item by differentiating it with the text color of the item or by using selection strip.

## Selection text color

The user can change the text color of the Selected item to desired color.The selected item text color can be customized by the [`SelectionTextColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~SelectionTextColor.html) property.

{% highlight c# %}

segmentedControl.SelectionTextColor = Color.ParseColor("#02A0AE");


{% endhighlight %}

![Xamarin.Android SfSegmentedControl selection text color](images/Selection-indicator/Xamarin_Android_selectiontextcolor.png)

## Selection Strip

A selection strip is used to indicate the selected item in the segmented control. The selection strip can be customized in many forms.

#### Position

The position of the selection indicator can be customized by the user in different ways.

##### Top

The selection strip can be displayed as a line with customizable color and thickness. It can be positioned at the top of an item.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Top;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selection Strip Top](images/Selection-indicator/Xamarin_Android_Top.png)

##### Bottom

As like Top placement selection strip can be customized by its color and thickness which can be positioned at the bottom of an item.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Bottom;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selection Strip Bottom](images/Selection-indicator/Xamarin_Android_Bottom.png)

##### Fill

The selection strip can be placed over a segment item to indicate it is selected. You can customize its color to highlight the item.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Fill;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selection Strip Fill](images/Selection-indicator/Xamarin_Android_Fill.png)

##### Border

The selection strip can be set as a border to highlight the selected item.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Border;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selection Strip Border](images/Selection-indicator/Xamarin_Android_Border.png)

#### Color

The background color of the selection strip can be customized using [`Color`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentItem~SelectionTextColor.html) property which is inside SelectionIndicatorSettings class.

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.ParseColor("#2C7BBC");
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

![Selection Strip Color](images/Selection-indicator/Xamarin_Android_stripcolor.png)

#### Thickness

The border thickness of the selection strip can be customized using [`Thickness`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfSegmentedControl~SegmentBorderThickness.html) property which is inside SelectionIndicatorSettings class

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.StrokeThickness = 10;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}





