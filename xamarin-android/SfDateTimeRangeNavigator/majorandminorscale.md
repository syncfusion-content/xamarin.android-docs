---
layout: post
title: Major and minor scale customization for DateTimeRangeNavigator
description: Major and minor scale customization
platform: Xamarin.Android
control: SfDateTimeRangeNavigator
documentation: ug
---

# Major and Minor Scales

SfDateTimeRangeNavigator displays major and minor scales at the top and bottom position of the control. You can also control its visibility using `MajorScaleStyle.Visible` and `MinorScaleStyle.Visible` properties.

## Intervals

By default, best possible interval component will be chosen for both major and minor scales based on the available size of the view. For example, if the available space is sufficient to show only year labels without overlapping, interval will be displayed in years. However, you can also set specific `DateTimeIntervalType` components using `Intervals` property as demonstrated in the below code snippet.

{% highlight c# %}
[C#]
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator(this);
dateTime.Intervals = EnumSet.Of(DateTimeIntervalType.Year, DateTimeIntervalType.Month);
{% endhighlight %}

![](majorandminorscale_images/minorandmajorscale_img1.png)

## Appearance Customization

The `MajorScaleStyle` and `MinorScaleStyle` properties of `SfDateTimeRangeNavigator` are used to customize the appearance of ticks and labels.

* `Position` - used to position the labels and ticks inside or outside of the range navigator.
* `LabelAlignment` - used to set the alignment of the labels. 
* `LabelTextColor` - used to change the text color of the labels.
* `LabelTextSize` -used to change the font size of the labels.
* `LabelTypeface` - used to change the font family and font weight
* `LabelMarginLeft` - used to change the left margin of the label.
* `LabelMarginTop` - used to change the top margin of the label.
* `LabelMarginRight` - used to change the right margin of the label.
* `LabelMarginBottom` - used to change the bottom margin of the label.
* `SelectedLabelTextColor` – used to change the text color of the selected label.
* `SelectedLabelTextSize` -used to change the font size of the labels.
* `SelectedLabelTypeface` - used to change the selected label’s font family and font weight
* `SelectedLabelMarginLeft` - used to change the left margin of the selected label.
* `SelectedLabelMarginTop` - used to change the top margin of the selected label.
* `SelectedLabelMarginRight` - used to change the right margin of the selected label.
* `SelectedLabelMarginBottom` - used to change the bottom margin of the selected label 

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

![](majorandminorscale_images/minorandmajorscale_img2.png)


