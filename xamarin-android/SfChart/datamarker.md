---
layout: post
title: Markers and data labels in Xamarin.Android Chart
description: Learn how to add markers and data point labels to a Chart series
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data points to the user. You can add a shape and label to adorn each data point. This can be enabled using following code snippet,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;

{% endhighlight %}

![](datamarker_images/datamarker_img1.png)

## Customizing Labels

The label appearance can be customized using following properties,

* `TextColor` – used to change the color of the label.
* `BackgroundColor` – used to change the label background color.
* `StrokeColor` – used to change the border color.
* `StrokeWidth` – used to change the width of the border.
* `TextSize` – used to change the text size.
* `Typeface` – used to change the font family and font weight.
* `MarginTop` - used to change the top margin of the labels.
* `MarginBottom` - used to change the bottom margin of the labels.
* `MarginLeft` - used to change the left margin of the labels.
* `MarginRight` - used to change the right margin of the labels.
* `Angle` – used to rotate the labels.
* `LabelPadding` - used to change the padding value of label.
* `OffsetX` - used to set the offset value of X.
* `OffsetY` - used to set the offset value of Y.

Following code snippet illustrates the customization of label and its background,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;
lineSeries.DataMarker.LabelStyle.TextColor = Color.Blue;
lineSeries.DataMarker.LabelStyle.BackgroundColor = Color.Cyan;
lineSeries.DataMarker.LabelStyle.StrokeColor = Color.Red;
lineSeries.DataMarker.LabelStyle.StrokeWidth = 2;
lineSeries.DataMarker.LabelStyle.TextSize = 18;
lineSeries.DataMarker.LabelStyle.Typeface = Typeface.DefaultFromStyle(TypefaceStyle.Italic);
lineSeries.DataMarker.LabelStyle.Angle = 315;
lineSeries.DataMarker.LabelStyle.MarginLeft = 5;
lineSeries.DataMarker.LabelStyle.MarginTop = 5;
lineSeries.DataMarker.LabelStyle.MarginRight = 5;
lineSeries.DataMarker.LabelStyle.MarginBottom = 5;

{% endhighlight %}

![](datamarker_images/datamarker_img2.png)

## Formatting Label Content

You can customize the content of the label using `LabelContent` property. Following are the two options that are supported now,

* `Percentage` – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* `YValue` – This will show the corresponding Y value.

{% highlight c# %} 
[C#]

pieSeries.DataMarker.LabelContent = LabelContent.Percentage;

{% endhighlight %}

![](datamarker_images/datamarker_img3.png)

## Label Position

This feature is used to position the data marker labels at Center, Inner and Outer position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using `OffsetX` and `OffsetY` properties respectively.

The following screenshot illustrates the default position of data marker labels,

![](datamarker_images/datamarker_img4.png)


The following code sample illustrates the center position of data marker labels,

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Center;

{% endhighlight %}

![](datamarker_images/datamarker_img5.png)

The following code sample illustrates the Inner position of data marker labels,

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Inner;

{% endhighlight %}

![](datamarker_images/datamarker_img6.png)


The following code sample illustrates the outer position of data marker labels, 

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Outer;

{% endhighlight %}

![](datamarker_images/datamarker_img7.png)

## Smart Labels

In Pie and Doughnut series, overlapping of data labels can be avoided by setting `SmartLabelsEnabled` property to true.

{% highlight c# %}
[C#]

SfChart chart = new SfChart();

PieSeries pieSeries = new PieSeries()
{

    DataSource = Data,
    StartAngle = 45,
    EndAngle = 405,
    SmartLabelsEnabled = true,
    ConnectorType = ConnectorType.Bezier,
    DataMarkerPosition = CircularSeriesDataMarkerPosition.OutsideExtended,

};

pieSeries.DataMarker.ShowLabel = true;

chart.Series.Add(pieSeries);

{% endhighlight %}

![](datamarker_images/datamarker_img10.png)

## Customizing Marker Shapes

Shapes can be added to chart data marker by setting the `ShowMarker` property to true. There are different shapes you can set to the chart using `MarkerType` property such as rectangle, circle, diamond etc. Following properties are used to customize marker appearance,

* `MarkerWidth` - used to change the width of the marker.
* `MarkerHeight` - used to change the height of the marker.
* `MarkerColor` - used to change the color of the marker.
* `MarkerStrokeColor` - used to change the border color of the shape.
* `MarkerStrokeWidth` – used to change the marker border width.

The following code example shows how to enable marker and specify its types,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = false;
lineSeries.DataMarker.ShowMarker = true;
lineSeries.DataMarker.MarkerType = DataMarkerType.Hexagon;
lineSeries.DataMarker.MarkerWidth = 20;
lineSeries.DataMarker.MarkerHeight = 20;
lineSeries.DataMarker.MarkerColor = Color.Cyan;
lineSeries.DataMarker.MarkerStrokeColor = Color.Red;
lineSeries.DataMarker.MarkerStrokeWidth = 2;

{% endhighlight %}

![](datamarker_images/datamarker_img8.png)


## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. Following properties used to customize connector line,

* `StrokeColor` – used to change the color of the line.
* `StrokeWidth` – used to change the stroke thickness of the line.
* `PathEffect` – used to set the dashes for the line.
* `ConnectorHeight` – used to change the connector line height.
* `ConnectorRotationAngle` – used to change the connector line rotation angle.

The following code illustrates how to specify the connector height and its angle,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;
lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight = 50;
lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;
lineSeries.DataMarker.ConnectorLineStyle.StrokeColor = Color.Blue;
lineSeries.DataMarker.ConnectorLineStyle.StrokeWidth = 3;
lineSeries.DataMarker.ConnectorLineStyle.PathEffect = new DashPathEffect(new float[] { 3, 3 }, 3);

{% endhighlight %}

![](datamarker_images/datamarker_img9.png)

N> For Pie and Doughnut series, you can set the Bezier curve for connector line using ConnectorType property of Pie and Doughnut series.