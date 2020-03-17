---
layout: post
title: Chart trendline | SfChart | Xamarin.Android | Syncfusion
description: How to configure the chart trendlines and customize the appearance of the trendlines in Xamarin.Android Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Trendlines in Xamarin.Android Chart

The [`Trendline`]() is a line drawn over the chart to display the overall direction of the results. And it built on the assumption based on current and past beliefs. 

The following code examples shows how to add Trendline in SfChart.

{% highlight c# %} 

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

## Types of Trendline

SfChart support following types of [`Trendlines`]().

* [`Linear`]()
* [`Exponential`]()
* [`Logarithmic`]()
* [`Power`]()
* [`Polynomial`]()


### Linear

[`Linear`]() trendline was best-fit straight line for simple linear datasets. A linear trend line usually shows that something is increasing or decreasing at a steady rate. This is the default trendline to be drawn for the SfChart.

The following is the code example of linear trendline.

{% tabs %} 
{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![Linear type trendline in Xamarin.Android Chart](trendline_images/trendline_linear.png)

### Logarithmic

A [`Logarithmic`]() trendline is the strongest-fit curved line, that is most effective when the data change rate increases or decreases rapidly. Logarithmic trends may use negative and/or positive values as well. 

The following is the code example of logarithmic trendline.

{% tabs %} 

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Logarithmic;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![Logarithmic type trendline in Xamarin.Android Chart](trendline_images/trendline_Logarithmic.png)

### Exponential

The [`Exponential`]() trendline is the curved line most useful for data values rise or fall at increasingly higher rates.

N> SfChart will not generate Exponential trendline when your data contains zero or negative values. 

{% tabs %} 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Exponential;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![Exponential type trendline in Xamarin.Android Chart](trendline_images/trendline_Exponential.png)

### Power

The [`Power`]() trendline is typically used with data sets to compare measurements that grow at a specific rate.

The following is the code example of power trendline.

{% tabs %} 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Power;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![Power type trendline in Xamarin.Android Chart](trendline_images/trendline_Power.png)

### Polynomial

The [`polynomial`]() trendline is a curved line that is used when there are more data fluctuations. By default, this trendline calculated with order of 2, it will be override by the property [`PolynomialOrder`]().

The following is the code example of polynomial trendline.

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Polynomial;
trendline.PolynomialOrder = 3;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![Polynomial type trendline in Xamarin.Android Chart](trendline_images/trendline_Polynomial.png)

## Forecasting

Forecasting is used to display trends about the future and the past beliefs.

The following two types of forecasting are available in SfChart:

* Forward Forecasting
* Backward Forecasting

### Forward Forecasting

For determining the future trends (in forward direction). The 
following code example explains the how to set the value for [`ForwardForecast`]().

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
trendline.ForwardForecast = 2;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![ForwardForecast in trendline Xamarin.Android Chart](trendline_images/trendline_Forward.png)

### Backward Forecast

For determining the future trends (in backward direction). The following code example explains the how to set the value for [`BackwardForecast`]().

{% tabs %} 

{% highlight c# %}
[C#]

columnSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline trendline = new ChartTrendline();
trendline.Type = ChartTrendlineType.Linear;
trendline.BackwardForecast = 2;
columnSeries.Trendlines.Add(trendline);

{% endhighlight %}

{% endtabs %}

![BackwardForecast in trendline Xamarin.Android Chart](trendline_images/trendline_Backward.png)

## Customization

We can customize the trendline appearance using [`StrokeWidth`](), [`StrokeColor`]() and [`PathEffect`]() properties. 

{% tabs %} 

{% highlight c# %}

trendline.StrokeColor = Color.Black;
trendline.StrokeWidth = 2;
trendline.PathEffect = new DashPathEffect(new float[] { 5, 6 }, 2);

{% endhighlight %}

{% endtabs %}

![Trendlines customizing appearence in Xamarin.Android Chart](trendline_images/trendline_customizing.png)

## Legend Item Visibility

We can able to control the visibility of the trendline legend items using [`VisibilityOnLegend`]() property of the Trendline.

{% tabs %} 

{% highlight c# %}

trendline.VisibilityOnLegend = Visibility.Visible;

{% endhighlight %}

{% endtabs %}

