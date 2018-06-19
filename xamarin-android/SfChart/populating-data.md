---
layout: post
title: Populating data
description: How to add data point to series in  Essential Xamarin.Android Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Populating Data

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) control can be configured with data points using [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~ItemsSource.html) property of [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries.html). You can assign a collection of custom objects to the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~ItemsSource.html) property. In this case, you need to set the [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~XBindingPath.html) and [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.XyDataSeries~YBindingPath.html) properties of chart series with the property names of the custom object which contains the x-value/category and y-value respectively.

N> While using custom objects, [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~XBindingPath.html) property is required for all types of chart series. You need to set [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.XyDataSeries~YBindingPath.html) property only for the [`XYDataSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.XyDataSeries.html) types which needs single y-value for a data point. For example, Line, Spline, Column, Bar, Pie etc.  For [`BubbleSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.BubbleSeries.html) type, you need to set both [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.XyDataSeries~YBindingPath.html) and [`Size`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.BubbleSeries~Size.html) properties since it requires two y-values to plot a single bubble data point. In the case of financial series types like Candle and HiLoOpenClose, which requires four y-values for a single data point, you need to set [`High`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FinancialSeriesBase~High.html), [`Low`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FinancialSeriesBase~Low.html), [`Open`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FinancialSeriesBase~Open.html) and [`Close`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.FinancialSeriesBase~Close.html) properties with the property names of a custom object which contains respective values.

Following code snippet illustrates this,

{% highlight c# %}
[C#]

public class MonthDemand

{

	public MonthDemand(string demand, double year2010, double year2011)
	{

		this.Demand = demand;

		this.Year2010 = year2010;

		this.Year2011 = year2011;

	}

	public string Demand { get; set; }

	public double Year2010 { get; set; }

	public double Year2011 { get; set; }

}

public class DataModel
{
	
	public ObservableCollection<MonthDemand>  Demands{ get; set; }

	public DataModel ()
	{

		Demands = new ObservableCollection<MonthDemand>();

		Demands.Add(new MonthDemand("Jan", 42, 27));
		Demands.Add(new MonthDemand("Feb", 44, 28));
		Demands.Add(new MonthDemand("Mar", 53, 35));
		Demands.Add(new MonthDemand("Apr", 64, 44));
		Demands.Add(new MonthDemand("May", 75, 54));
		Demands.Add(new MonthDemand("Jun", 83, 63));
		Demands.Add(new MonthDemand("Jul", 87, 68));
		Demands.Add(new MonthDemand("Aug", 84, 66));
		Demands.Add(new MonthDemand("Sep", 78, 59));
		Demands.Add(new MonthDemand("Oct", 67, 48));
		Demands.Add(new MonthDemand("Nov", 55, 38));
		Demands.Add(new MonthDemand("Dec", 45, 29));

	}

}   

{% endhighlight %}

{% highlight c# %}
[C#]

chart.Series.Add (new ColumnSeries () {
	
	ItemsSource = dataModel.Demands,

	XBindingPath = "Demand",

	YBindingPath = "Year2010"

});

{% endhighlight %}