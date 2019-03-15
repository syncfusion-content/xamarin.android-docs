---
layout: post
title: Chart Trackball in Syncfusion SfChart
description: How to enable and customize the trackball behavior in Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Trackball

Trackball feature displays the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used instead of data label feature when you cannot show data labels for all data points due to space constraint. To enable this feature, add an instance of [`ChartTrackballBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html) to the [`Behaviors`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Behaviors.html) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html). Trackball will be activated once you long-press anywhere on the chart area. Once it is activated, it will appear in the UI and move based on your touch movement until you stop touching on the chart.

You can use the following properties to show/hide the line and labels.

* [`ShowLabel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLabel.html) – Shows/hides trackball label. Default value is true.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLine.html) – Shows/hides the trackball line. Default value is true.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();
trackballBehavior.ShowLabel = true;
trackballBehavior.ShowLine = true;

chart.Behaviors.Add(trackballBehavior);

{% endhighlight %}

![Trackball support in Xamarin.Android Chart](trackball_images/trackball_img1.png)

## Label Display Mode

[`LabelDisplayMode`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~LabelDisplayMode.html) property is used to specify whether to display label for all the data points along the vertical line or display only single label. Following are the three options you can set to this property,

* [`FloatAllPoints`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.TrackballLabelDisplayMode.html) – Displays label for all the data points along the vertical line.
* `NearestPoint` – Displays label for single data point that is nearer to the touch contact position.
* `GroupAllPoints` - Displays label for all the data points are grouped and positioned at the top of the chart area.

{% highlight c# %} 
[C#]

trackballBehavior.LabelDisplayMode = TrackballLabelDisplayMode.NearestPoint;

{% endhighlight %}

In the following screenshot, trackball label is shown for only single data point,

![Label display mode support for trackball in Xamarin.Android Chart](trackball_images/trackball_img2.png)

## Activation mode

The [`ActivationMode`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ActivationMode.html) property is used to restrict the visibility of trackball based on the touch actions. The default value of this property is [`ChartTrackballActivationMode.LongPress`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballActivationMode.html).

The ChartTrackballActivationMode enum contains the following values:

* [`LongPress`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballActivationMode.html) – Activates trackball only when performing the long press action.
* [`TouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballActivationMode.html) – Activates trackball only when performing touch move action.
* [`None`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballActivationMode.html) – Hides the visibility of trackball when setting activation mode to [`None`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballActivationMode.html). It will be activated when calling the [`Show`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~Show.html) method.

## Customizing appearance

**Customize Trackball Labels**

The [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~LabelStyle.html) property provides options to customize the trackball labels.

* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~TextColor.html) – used to change the color of the labels.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~BackgroundColor.html) – used to change the label background color.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeColor.html) – used to change the border color.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeWidth.html) – used to change the thickness of the border.
* [`TextSize`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~TextSize.html) – used to change the text size.
* [`Typeface`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~Typeface.html) – used to change the font family and font weight.
* [`MarginTop`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginTop.html) - used to change the top margin of the labels.
* [`MarginBottom`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginBottom.html) - used to change the bottom margin of the labels.
* [`MarginLeft`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginLeft.html) - used to change the left margin of the labels.
* [`MarginRight`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginRight.html) - used to change the right margin of the labels.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();

trackballBehavior.LabelStyle.BackgroundColor = Color.Cyan;

trackballBehavior.LabelStyle.StrokeColor = Color.ParseColor("#FF8C0707");

trackballBehavior.LabelStyle.StrokeWidth = 2;

trackballBehavior.LabelStyle.TextColor = Color.Red;

trackballBehavior.LabelStyle.TextSize = 18;

chart.Behaviors.Add(trackballBehavior);

{% endhighlight %}


**Customize Trackball Marker**

The [`MarkerStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~MarkerStyle.html) property provides options to customize the trackball markers.

Following properties are used to customize the trackball marker.

* [`ShowMarker`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~ShowMarker.html) – used to enable / disable the marker. Default value is true.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~StrokeColor.html) – used to change the marker stroke color.
* [`Color`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Color.html) – used to change the marker background color.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~StrokeWidth.html) – used to change the width of the marker stroke.
* [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Width.html) – used to change the width of the marker.
* [`Height`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Height.html) – used to change the height of the marker.
* [`MarkerType`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~MarkerType.html) - used to change the type of the marker such as [`Cross`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.MarkerType.html), Ellipse, Diamond etc.

{% highlight c# %} 

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();

trackballBehavior.MarkerStyle.StrokeColor = Color.Purple;

trackballBehavior.MarkerStyle.StrokeWidth = 1;

trackballBehavior.MarkerStyle.ShowMarker = true;

trackballBehavior.MarkerStyle.Height = 8;

trackballBehavior.MarkerStyle.Width = 8;

trackballBehavior.MarkerStyle.Color = Color.Green;

chart.Behaviors.Add(trackballBehavior);

{% endhighlight %}

**Customize Trackball Line**

The [`LineStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~LineStyle.html) property provides options to customize the trackball line.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLine.html) – used to enable / disable the line. Default value is true.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~StrokeWidth.html) – used to change the stroke width of the line.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~StrokeColor.html) – used to change the stroke color of the line.
* [`PathEffect`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~PathEffect.html) – Specifies the dashes to be applied on the line.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();

trackballBehavior.ShowLine = true;
     
trackballBehavior.LineStyle.StrokeWidth = 2;
     
trackballBehavior.LineStyle.StrokeColor = Color.Blue;

trackballBehavior.LineStyle.PathEffect = new DashPathEffect(new float[] { 2, 3 }, 3);

chart.Behaviors.Add(trackballBehavior);

{% endhighlight %}

Following screenshot illustrates the customization of trackball elements.

![Customizing the appearance of trackball label in Xamarin.Android Chart](trackball_images/trackball_img3.png)

**Custom View**

You can customize the appearance of Trackball label with your own view by overriding [`GetView`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~GetView(ChartSeries,Object,Int32).html) method of [`ChartTrackballBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html). You can get the respective series, underlying object and index of the data point from argument of [`GetView`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~GetView(ChartSeries,Object,Int32).html) method.

{% highlight c# %} 
[C#]

protected override View GetView(ChartSeries series, object data, int index)
        {
            LinearLayout parentLayout = new LinearLayout(Chart.Context);
            parentLayout.SetPadding(2, 2, 2, 2);
            parentLayout.Orientation = Orientation.Horizontal;
            LinearLayout layout = new LinearLayout(Chart.Context);
            layout.Orientation = Orientation.Vertical;

            ImageView image = new ImageView(Chart.Context);
            image.LayoutParameters = new ViewGroup.LayoutParams(new LinearLayout.LayoutParams
                ((int)(Chart.Context.Resources.DisplayMetrics.Density * 40), (int)(Chart.Context.Resources.DisplayMetrics.Density * 40)));
            image.SetPadding(0, 2, 0, 2);
            image.SetImageResource(Resource.Drawable.grain);

            TextView text1 = new TextView(Chart.Context);
            text1.SetTextColor(Color.White);
            text1.Text = (data as Model).YValue + "%";
            text1.TextSize = 12;
            text1.SetTypeface(Typeface.SansSerif, TypefaceStyle.Bold);
            layout.AddView(text1);

            TextView text2 = new TextView(Chart.Context);
            text2.Text = "Efficiency";
            text2.TextSize = 10;
            text2.SetTextColor(Color.White);
            layout.AddView(text2);
            layout.SetPadding(5, (int)(Chart.Context.Resources.DisplayMetrics.Density * 5), 2, 0);

            parentLayout.AddView(image);
            parentLayout.AddView(layout);

            return parentLayout;
        }

{% endhighlight %}

![Customizing the view of trackball label in Xamarin.Android Chart](trackball_images/trackball_img5.png)

### Show/hide the trackball label in axis

This feature is used to highlight the respective axis label when the trackball is moving across the axis. [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~ShowTrackballInfo.html) property is used to show/hide the trackball label of the axis. [`TrackballLabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~TrackballLabelStyle.html) property is used to customize its appearance. Default value of [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~ShowTrackballInfo.html) is False.

{% highlight c# %} 
[C#]

chart.PrimaryAxis = new NumericalAxis()
{
    ShowTrackballInfo = true
};
			
{% endhighlight %}

### Axis label alignment

The position of trackball’s axis label can be changed using the [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballAxisLabelStyle~LabelAlignment.html) property of [`ChartTrackballAxisLabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballAxisLabelStyle.html). The following options are available in [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballAxisLabelStyle~LabelAlignment.html).

* [`Far`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelAlignment.html) - The label will be positioned below the tick in vertical axis and right of the tick in horizontal axis.
* [`Near`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelAlignment.html) - The label will be positioned above the tick in vertical axis and left of the tick in horizontal axis.
* [`Center`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelAlignment.html) - The label will be positioned at the center of tick. This is the default value.

The following code snippet demonstrate the placement of label at the left to tick line.

{% highlight c# %} 
[C#]

  primaryAxis.TrackballLabelStyle.LabelAlignment = ChartLabelAlignment.Near;
  
{% endhighlight %}

### Show/hide the series label

This feature is used to show/hide the trackball label of the series by using [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~ShowTrackballInfo.html) property. Default value of [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.CartesianSeries~ShowTrackballInfo.html) property is True.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value",
    ShowTrackballInfo = false

};
chart.Series.Add(lineSeries);

{% endhighlight %}

## Method

**OnLabelsGenerated**

To customize the appearance of trackball label based on condition, override the OnLabelsGenerated method of [`ChartTrackballBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html). The argument of this method is [`ChartPointInfo`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo.html), which contains the following properties: 

* [`Label`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~Label.html) - Used to provide text for trackball label.
* [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~IsVisible.html) - Determines the visibility of trackball.
* [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~Series.html) - Gets the respective series of the data point in which the trackball is activated.
* [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~LabelStyle.html) - Customizes the appearance of trackball label.
* [`ChartDataPoint`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~ChartDataPoint.html) - Gets the respective underlying object of the data in which the trackball is activated.
* [`DataPointIndex`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~DataPointIndex.html) - Gets the index of the selected data point.
* [`XPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~XPosition.html) - Gets the x-position of trackball label.
* [`YPosition`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~YPosition.html) - Gets the y-position of trackball label.
* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartPointInfo~Color.html) - Gets the default color of trackball label.

### Show method

The [`Show`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~Show.html) method is used to activate the trackball at the specified location.

{% highlight c# %} 
[C#]

trackball.Show(pointX, pointY);

{% endhighlight %}

### Hide method

The [`Hide`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~Hide.html) method is used to hide the trackball programmatically.

{% highlight c# %} 
[C#]

trackball.Hide();

{% endhighlight %}

### HitTest method

The [`HitTest`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~HitTest.html) method is used to check whether the point is in trackball or not.

{% highlight c# %} 
[C#]

trackball.HitTest(pointX, pointY);

{% endhighlight %}

### Get the touch position

The [`OnLongPress(float valueX, float valueY)`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~OnLongPress.html) method of [`ChartTrackballBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html) can be override to get the touch points while doing interactions.
