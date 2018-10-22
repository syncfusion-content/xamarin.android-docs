---
layout: post
title: Major and minor scale customization for DateTimeRangeNavigator
description: Major and minor scale customization
platform: Xamarin.Android
control: SfDateTimeRangeNavigator
documentation: ug
---

# Major and Minor Scales

SfDateTimeRangeNavigator displays major and minor scales at the top and bottom position of the control. You can also control its visibility using [`MajorScaleStyle.Visible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~Visible.html) and [`MinorScaleStyle.Visible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~Visible.html) properties.

## Intervals

By default, best possible interval component will be chosen for both major and minor scales based on the available size of the view. For example, if the available space is sufficient to show only year labels without overlapping, interval will be displayed in years. However, you can also set specific [`DateTimeIntervalType`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.DateTimeIntervalType.html) components using [`Intervals`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~Intervals.html) property as demonstrated in the below code snippet.

{% highlight c# %}
[C#]
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator(this);
dateTime.Intervals = EnumSet.Of(DateTimeIntervalType.Year, DateTimeIntervalType.Month);
{% endhighlight %}

![Interval support for major and minor scales in Xamarin.Android DateTimeRangeNavigator](majorandminorscale_images/minorandmajorscale_img1.png)

## Appearance Customization

The [`MajorScaleStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~MajorScaleStyle.html) and [`MinorScaleStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~MinorScaleStyle.html) properties of `SfDateTimeRangeNavigator` are used to customize the appearance of ticks and labels.

* [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~Position.html) - used to position the labels and ticks [`Inside`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScalePosition.html) or [`Outside`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScalePosition.html) of the range navigator.
* [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelAlignment.html) - used to set the alignment of the labels([`Center`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.LabelAlignment.html), Left, Right).  
* [`LabelTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelTextColor.html) - used to change the text color of the labels.
* [`LabelBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelBackgroundColor.html) - used to change the background color of the labels.
* [`LabelStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelStrokeColor.html) - used to change the stroke color of the labels.
* [`LabelStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelStrokeWidth.html) - used to change the stroke width of the labels.
* [`LabelTextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelTextSize.html) -used to change the font size of the labels.
* [`LabelTypeface`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelTypeface.html) - used to change the font family and font weight
* [`LabelMarginLeft`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelMarginLeft.html) - used to change the left margin of the label.
* [`LabelMarginTop`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelMarginTop.html) - used to change the top margin of the label.
* [`LabelMarginRight`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelMarginRight.html) - used to change the right margin of the label.
* [`LabelMarginBottom`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~LabelMarginBottom.html) - used to change the bottom margin of the label.
* [`SelectedLabelTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelTextColor.html) – used to change the text color of the selected label.
* [`SelectedLabelBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelBackgroundColor.html) - used to change the background color of the selected label.
* [`SelectedLabelStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelStrokeColor.html) - used to change the stroke color of the selected label.
* [`SelectedLabelStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelStrokeWidth.html) - used to change the stroke width of the selected label.
* [`SelectedLabelTextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelTextSize.html) -used to change the font size of the labels.
* [`SelectedLabelTypeface`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelTypeface.html) - used to change the selected label’s font family and font weight
* [`SelectedLabelMarginLeft`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelMarginLeft.html) - used to change the left margin of the selected label.
* [`SelectedLabelMarginTop`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelMarginTop.html) - used to change the top margin of the selected label.
* [`SelectedLabelMarginRight`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelMarginRight.html) - used to change the right margin of the selected label.
* [`SelectedLabelMarginBottom`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~SelectedLabelMarginBottom.html) - used to change the bottom margin of the selected label.
* [`TickLineWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~TickLineWidth.html) - used to change the thickness of the tick line.
* [`TickLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.ScaleStyle~TickLineColor.html) - used to change the color of the tick line.

{% highlight c# %}
[C#]
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator();
dateTime.MajorScaleStyle.Position = ScalePosition.Inside;
dateTime.MajorScaleStyle.LabelTextColor = Color.Black;
dateTime.MajorScaleStyle.LabelMarginLeft = 15;
dateTime.MajorScaleStyle.LabelMarginTop = 15;
dateTime.MajorScaleStyle.LabelMarginRight = 15;
dateTime.MajorScaleStyle.LabelMarginBottom = 15;
dateTime.MajorScaleStyle.LabelTextSize = 20;
dateTime.MajorScaleStyle.LabelAlignment = LabelAlignment.Right;
dateTime.MajorScaleStyle.SelectedLabelTextColor = Color.Red;
dateTime.MajorScaleStyle.SelectedLabelMarginLeft = 15;
dateTime.MajorScaleStyle.SelectedLabelMarginTop = 15;
dateTime.MajorScaleStyle.SelectedLabelMarginRight = 15;
dateTime.MajorScaleStyle.SelectedLabelMarginBottom = 15;
dateTime.MajorScaleStyle.SelectedLabelTextSize = 20;
dateTime.MinorScaleStyle.Position = ScalePosition.Inside;
dateTime.MinorScaleStyle.LabelTextColor = Color.Black;
dateTime.MinorScaleStyle.LabelMarginLeft = 15;
dateTime.MinorScaleStyle.LabelMarginTop = 15;
dateTime.MinorScaleStyle.LabelMarginRight = 15;
dateTime.MinorScaleStyle.LabelMarginBottom = 15;
dateTime.MinorScaleStyle.LabelTextSize = 20;
dateTime.MinorScaleStyle.LabelAlignment = LabelAlignment.Left;
dateTime.MinorScaleStyle.SelectedLabelTextColor = Color.Blue;
dateTime.MinorScaleStyle.SelectedLabelMarginLeft = 15;
dateTime.MinorScaleStyle.SelectedLabelMarginTop = 15;
dateTime.MinorScaleStyle.SelectedLabelMarginRight = 15;
dateTime.MinorScaleStyle.SelectedLabelMarginBottom = 15;
dateTime.MinorScaleStyle.SelectedLabelFontSize = 20;
{% endhighlight %}

![Customizing the appearance of ticks and labels in Xamarin.Android DateTimeRangeNavigator](majorandminorscale_images/minorandmajorscale_img2.png)

## Events

### MajorScaleLabelsCreate

The [`MajorScaleLabelsCreate`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~MajorScaleLabelsCreate_EV.html) event is triggered when the major scale label is created. The argument contains [`MajorScaleLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator+MajorScaleLabelsCreateEventArgs~MajorScaleLabels.html) of [`RangeNavigatorLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel.html) which contains following properties:

* [`GridLinePosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~GridLinePosition.html) - Used to get the position of grid lines. 
* [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~IsVisible.html) - Used to define the visibility of labels.
* [`LabelContent`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~LabelContent.html) - Used to determine the content of labels.
* [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~LabelPosition.html) - Used to get the position of labels. 

### MinorScaleLabelsCreate

The [`MinorScaleLabelsCreate`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator~MinorScaleLabelsCreate_EV.html) event is triggered when the minor scale label is created. The argument contains [`MinorScaleLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator+MinorScaleLabelsCreateEventArgs~MinorScaleLabels.html) of [`RangeNavigatorLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel.html) which contains following properties:

* [`GridLinePosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~GridLinePosition.html) - Used to get the position of grid lines. 
* [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~IsVisible.html) - Used to define the visibility of labels.
* [`LabelContent`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~LabelContent.html) - Used to determine the content of labels.
* [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Rangenavigator.RangeNavigatorLabel~LabelPosition.html) - Used to get the position of labels. 

