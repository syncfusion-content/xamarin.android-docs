---
layout: post
title: Chart StripLines
description: Learn how to add horizontal or vertical lines in Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Strip Lines

## What is strip line?

Strip lines are used to shade the different ranges in plot area in different colors to improve the readability of the chart. You can annotate it with text to indicate what that particular region indicates. You can also enable the strip lines to be drawn repeatedly at regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart.

## How to add strip lines?

Strip line is classified into **NumericalStripLine** and **DateTimeStripLine** based on the type of input you provide to draw the strip line. Since strip lines are drawn based on the axis, you have to add strip line instance using StripLines property of the respective axis. You can also add multiple strip lines to an axis.

Following properties are used to configure the strip line.

* [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine~Start.html) – used to change the start position of the strip line.
* [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Width.html) – used to change how long strip line should expand.
* [`WidthType`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeStripLine~WidthType.html) - used to change the date time unit of the value specified in the width property.
* [`PixelWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~PixelWidth.html) - used to specify the unit type for Width property, whether it is screen point or chart value.
* [`Text`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Text.html) – used to change the text of the strip line.
* [`FillColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~FillColor.html) – used to change the fill color of the strip line.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~StrokeWidth.html) – used to change the stroke width of the strip line.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~StrokeColor.html) – used to change the stroke color of the strip line.
* [`StrokePathEffect`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~StrokePathEffect.html) - used to render the strip line with dashes.
* [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~CornerRadius.html) - used to customize the corner radius of the rectangle.

**NumericalStripLine**

[`NumericalStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine.html) are used to draw strip lines for [`NumericalAxis`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalAxis.html) and [`CategoryAxis`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CategoryAxis.html). To add a strip line, create an instance of [`NumericalStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine.html) and add to the axis using [`StripLines`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalAxis~StripLines.html) property of the respective axis.

{% highlight c# %}
[C#]
 
SfChart chart = new SfChart();
...

NumericalAxis numericalAxis = new NumericalAxis();

numericalAxis.Minimum = 28;

numericalAxis.Maximum = 52;

NumericalStripLine numericalStripLines = new NumericalStripLine();

numericalStripLines.Start = 36;

numericalStripLines.Width = 8;

numericalStripLines.Text = "Average Temperature";

numericalStripLines.FillColor = Color.ParseColor("#F4C762");

numericalAxis.StripLines.Add(numericalStripLines);

chart.SecondaryAxis = numericalAxis;

{% endhighlight %}

![](striplines_images/stripline_img1.png)

**DateTimeStripLine**

As the name indicates, [`DateTimeStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeStripLine.html) are used to draw strip lines for [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeAxis.html). To add a strip line for [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeAxis.html), create an instance of [`DateTimeStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeStripLine.html) and add to the axis using [`StripLines`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeAxis~StripLines.html) property of [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.DateTimeAxis.html).

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

DateTimeAxis dateTimeAxis = new DateTimeAxis()
{
    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Interval = 3,
    IntervalType = DateTimeIntervalType.Months
};

Calendar calendar = new GregorianCalendar(2000, 0, 1);
dateTimeAxis.Minimum = calendar.Time;
calendar.Set(2000, 11, 30);
dateTimeAxis.Maximum = calendar.Time;

DateTimeStripLine dateTimeStripLine = new DateTimeStripLine()
{
    WidthType = DateTimeIntervalType.Months,              
    Width = 3,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#3FAA38")
};


calendar.Set(2000, 4, 1);
dateTimeStripLine.Start = calendar.Time;
dateTimeAxis.StripLines.Add(dateTimeStripLine);

chart.PrimaryAxis = dateTimeAxis;

{% endhighlight %}

![](striplines_images/stripline_img2.png)

## Strip Line Recurrence

This feature is used to enable the strip lines to be drawn repeatedly at the regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart. Following properties are used to configure this feature.

* [`RepeatEvery`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~RepeatEvery.html) – used to change the frequency of the strip line being repeated.
* [`RepeatUntil`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine~RepeatUntil.html) – specifies the end value at which point strip line has to stop repeating.

Following code snippet and screenshot demonstrates this feature by highlighting weekends. 

{% highlight c# %} 
[C#]

NumericalStripLine numericalStripLines = new NumericalStripLine();

numericalStripLines.Start = 6;

numericalStripLines.Width = 1;

numericalStripLines.Text = "Weekend";

numericalStripLines.FillColor = Color.ParseColor("#ECE6F1");

numericalStripLines.RepeatEvery = 7;

numericalStripLines.LabelStyle.Angle = 270;

numericalStripLines.LabelStyle.TextColor = Color.Red;

{% endhighlight %}

![](striplines_images/stripline_img3.png)

## Customize Text

The [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~LabelStyle.html) property provide options to customize the font-family, color, size and font-weight of strip line text. Following are the options available,

* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~TextColor.html) – used to change the color of the text.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~BackgroundColor.html) – used to change the label background color.
* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeColor.html) – used to change the border color.
* [`BorderThickness`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeWidth.html) – used to change the thickness of the border.
* [`Font`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~Typeface.html) – used to change the text size, font family and font weight.
* [`Margin`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginBottom.html) - used to change the margin size for text.
* [`Angle`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLineLabelStyle~Angle.html) – used to rotate the text.
* [`HorizontalAlignment`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLineLabelStyle~HorizontalLabelAlignment.html) – used to change the horizontal alignment of text.
* [`VerticalAlignment`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLineLabelStyle~VerticalLabelAlignment.html)  - used to change the vertical alignment of text.

{% highlight c# %} 
[C#]

NumericalAxis numericalAxis = new NumericalAxis()
{
    Minimum = 30,
    Maximum = 48
};

NumericalStripLine numericalStripLines = new NumericalStripLine()
{
    Start = 42,
    Width = 6,
    Text = "High Temperature",
    FillColor = Color.ParseColor("#EF7878")                
};

numericalStripLines.LabelStyle.TextSize = 20;
numericalStripLines.LabelStyle.TextColor = Color.Blue;

numericalAxis.StripLines.Add(numericalStripLines);

{% endhighlight %}

![](striplines_images/stripline_img4.png)

## Segmented Strip Line

Typically, if you draw a strip line for a vertical axis, the height of the strip line is determined by the [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine~Start.html) and [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Width.html) properties and width of the strip line is equivalent to the width of its associated horizontal axis i.e., strip line is drawn horizontally to the entire stretch of its associated horizontal axis. Similarly, for horizontal axis, width is determined by [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.NumericalStripLine~Start.html) and [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Width.html) properties, and vertically, it is drawn to the entire stretch of the associated vertical axis.

Suppose, you want to draw a strip line that should not stretch along its associated axis, you can customize using [`SegmentStart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentStart.html) and [`SegmentEnd`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentEnd.html) properties. Values provided in these two properties correspond to its associated axis specified using [`SegmentAxisName`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentAxisName.html) property. Finally, you need to set [`Segmented`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Segmented.html) property to true to indicate that strip line should be drawn as a segment.

* [`Segmented`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~Segmented.html) – Used to enable / disable the segmented strip line.
* [`SegmentStart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentStart.html) – Used to change the segment start value. Value correspond to associated axis.
* [`SegmentEnd`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentEnd.html) – Used to change the segment end value. Value correspond to associated axis.
* [`SegmentAxisName`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentAxisName.html) – Specify the name of the associated axis name.

N> You can set the double or DateTime value for [`SegmentStart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentStart.html) and [`SegmentEnd`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartStripLine~SegmentEnd.html) properties based on the associated axis type.

Following code snippet shows how to set the segment start and end value if the associated axis type is numerical.

{% highlight c# %}
[C#]
 
SfChart chart = new SfChart();
...

CategoryAxis categoryAxis = new CategoryAxis()
{
    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Interval = 3
};

NumericalStripLine numericalStripLines = new NumericalStripLine()
{
    Segmented = true,
    SegmentStart = 40,
    SegmentEnd = 46,
    SegmentAxisName = "Amount",
    Start = 3,
    Width = 3,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#EF7878")
};

categoryAxis.StripLines.Add(numericalStripLines);
chart.PrimaryAxis = categoryAxis;

chart.SecondaryAxis = new NumericalAxis()
{
    Minimum = 30,
    Maximum = 48,
    Name = "Amount"
};

{% endhighlight %}

![](striplines_images/stripline_img5.png)

Following code snippet shows how to set the segment start and end value if the associated axis type is date time. 

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

chart.PrimaryAxis = new DateTimeAxis()
{

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Name = "Period"

};

NumericalStripLine stripLine = new NumericalStripLine()
{

    Start = 42,
    Width = 4,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#3FAA38"),
    Segmented = true,
    SegmentAxisName = "Period"             
};

Calendar calendar = new GregorianCalendar(2000, 3, 1);
stripLine.SegmentStart = calendar;
calendar.Set(2000, 5, 30);
stripLine.SegmentEnd = calendar;

NumericalAxis numericalAxis = new NumericalAxis()
{

    Minimum = 30,
    Maximum = 48

};

numericalAxis.StripLines.Add(stripLine);

chart.SecondaryAxis = numericalAxis;

{% endhighlight %}

![](striplines_images/stripline_img6.png)