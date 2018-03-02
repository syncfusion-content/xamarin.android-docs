---
layout: post
title: Chart Trackball
description: How to enable and customize the trackball behavior in Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Trackball

Trackball feature displays the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used instead of data label feature when you cannot show data labels for all data points due to space constraint. To enable this feature, add an instance of [`ChartTrackballBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html) to the [`Behaviors`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBehavior.html) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html). Trackball will be activated once you long-press anywhere on the chart area. Once it is activated, it will appear in the UI and move based on your touch movement until you stop touching on the chart.

You can use the following properties to show/hide the line and labels.

* [`ShowLabel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLabel.html) – Shows/hides trackball label. Default value is true.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLine.html) – Shows/hides the trackball line. Default value is true.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();
trackballBehavior.ShowLabel = true;
trackballBehavior.ShowLine = true;

chart.Behaviors.Add(trackballBehavior);

{% endhighlight %}

![](trackball_images/trackball_img1.png)

## Label Display Mode

[`LabelDisplayMode`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~LabelDisplayMode.html) property is used to specify whether to display label for all the data points along the vertical line or display only single label. Following are the three options you can set to this property,

* `FloatAllPoints` – Displays label for all the data points along the vertical line.
* `NearestPoint` – Displays label for single data point that is nearer to the touch contact position.
* `GroupAllPoints` - Displays label for all the data points are grouped and positioned at the top of the chart area.

{% highlight c# %} 
[C#]

trackballBehavior.LabelDisplayMode = TrackballLabelDisplayMode.NearestPoint;

{% endhighlight %}

In the following screenshot, trackball label is shown for only single data point,

![](trackball_images/trackball_img2.png)

## Customizing appearance

**Customize Trackball Labels**

Following properties are used to customize the trackball labels.

* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~TextColor.html) – used to change the color of the labels.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~BackgroundColor.html) – used to change the label background color.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeColor.html) – used to change the border color.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~StrokeWidth.html) – used to change the thickness of the border.
* [`TextSize`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~TextSize.html) – used to change the text size.
* [`Typeface`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~Typeface.html) – used to change the font family and font weight.
* [`MarginTop`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginTop.html) - used to change the top margin of the labels.
* [`MarginBottom`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginBottom.html) - used to change the bottom margin of the labels.
* [`MarginLeft`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginLeft.html) - used to change the left margin of the labels.
* [`MarginRight`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLabelStyle~MarginRight.html) - used to change the right margin of the labels.

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

Following properties are used to customize the trackball marker.

* [`ShowMarker`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~ShowMarker.html) – used to enable / disable the marker. Default value is true.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~StrokeColor.html) – used to change the marker stroke color.
* [`Color`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Color.html) – used to change the marker background color.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~StrokeWidth.html) – used to change the width of the marker stroke.
* [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Width.html) – used to change the width of the marker.
* [`Height`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballMarkerStyle~Height.html) – used to change the height of the marker.

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

Following properties are used to customize the trackball line.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~ShowLine.html) – used to enable / disable the line. Default value is true.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~StrokeWidth.html) – used to change the stroke width of the line.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~StrokeColor.html) – used to change the stroke color of the line.
* [`PathEffect`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartLineStyle~PathEffect.html) – Specifies the dashes to be applied on the line.

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

![](trackball_images/trackball_img3.png)

**Custom View**

You can customize the appearance of Trackball label with your own view by overriding [`GetView`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~GetView(ChartSeries,Object,Int32).html) method of [`ChartTrackballBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior.html). You can get the respective series, underlying object and index of the data point from argument of [`GetView`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~GetView(ChartSeries,Object,Int32).html) method.

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

![](trackball_images/trackball_img5.png)