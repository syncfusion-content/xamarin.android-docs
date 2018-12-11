---
layout: post
title: Getting Started for Essential Xamarin.Android Chart | Syncfusion
description: getting started
platform: Xamarin.Android
control: SfChart
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the Chart with data, title, add data labels and tooltips to the Chart. This section covers only the minimal features that you need to know to get started with the Chart.

## Adding Chart Reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio\15.3.0.26\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfChart.Android.dll

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [`link`](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Initialize Chart

You can add the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) to an XML designer from the toolbox and the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) can be customized in designer using the property window.

![SfChart Designer support in Xamarin.Android](Getting-Started_images/designer.gif)

You can get the chart instance from axml page in MainActivity using the following code.

{% highlight C# %}

SfChart chart = FindViewById<SfChart>(Resource.Id.sfChart1);

{% endhighlight %}

You can create chart using code behind also. The following steps help to add chart using code behind.

Import the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) namespace as shown below in your respective Page,

{% highlight C# %}

using Com.Syncfusion.Charts;

{% endhighlight %}

Then initialize an empty chart with [`PrimaryAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~PrimaryAxis.html) and [`SecondaryAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~SecondaryAxis.html) as shown below,

{% highlight C# %} 

SfChart chart = new SfChart (this);

//Initializing Primary Axis
CategoryAxis primaryAxis = new CategoryAxis ();

chart.PrimaryAxis = primaryAxis;

//Initializing Secondary Axis
NumericalAxis secondaryAxis = new NumericalAxis ();

chart.SecondaryAxis = secondaryAxis;

SetContentView(chart);

{% endhighlight %}

Run the project and check if you get following output to make sure you have configured your project properly to add [`SfChart`.](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html)

![Adding Xamarin.Android Chart reference](Getting-Started_images/img1.png)

## Initialize view model

Now, let us define a simple data model that represents a data point in [`SfChart`.](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html)

{% highlight c# %}
public class Person   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}
{% endhighlight %} 

Next, create a view model class and initialize a list of `Person` objects as shown below,

{% highlight c# %}
public class ViewModel  
{
      public ObservableCollection<Person> Data { get; set; }      

      public ViewModel()       
      {
            Data = new ObservableCollection<Person>()
            {
                new Person { Name = "David", Height = 180 },
                new Person { Name = "Michael", Height = 170 },
                new Person { Name = "Steve", Height = 160 },
                new Person { Name = "Joel", Height = 182 }
            }; 
       }
 }
{% endhighlight %} 

## Populate Chart with data

As we are going to visualize the comparison of heights in the data model, add [`ColumnSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ColumnSeries.html) to [`SfChart.Series`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Series.html) property, and then set the Data property of the above `ViewModel` to the [`ColumnSeries.ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~ItemsSource.html) property as shown below.

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~XBindingPath.html) and [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.XyDataSeries~YBindingPath.html) properties, so that [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) would fetch values from the respective properties in the data model to plot the series.

{% highlight C# %}
//Initializing primary axis
CategoryAxis primaryAxis = new CategoryAxis();

primaryAxis.Title.Text = "Name";

chart.PrimaryAxis = primaryAxis;

//Initializing secondary Axis
NumericalAxis secondaryAxis = new NumericalAxis();

secondaryAxis.Title.Text = "Height (in cm)";

chart.SecondaryAxis = secondaryAxis;

//Initializing column series
ColumnSeries series = new ColumnSeries();

ViewModel viewModel = new ViewModel();

series.ItemsSource = viewModel.Data;

series.XBindingPath = "Name";

series.YBindingPath = "Height";

chart.Series.Add(series);
{% endhighlight %}

## Add Title

You can add title to chart to provide quick information to the user about the data being plotted in the chart. You can set title using [`SfChart.Title`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Title.html) property as shown below.

{% highlight C# %}
 
chart.Title.Text = "Chart";

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/charttitle) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) to customize chart title.

## Enable data labels

You can add data labels to improve the readability of the chart. This can be achieved using [`ChartSeries.DataMarker.ShowLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartDataMarker~ShowLabel.html) property as shown below.

{% highlight C# %} 

series.DataMarker.ShowLabel = true;

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/datamarker) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) to customize data markers.

## Enable legend

You can enable legend using [`SfChart.Legend`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart~Legend.html) property as shown below,

{% highlight C# %} 

chart.Legend.Visibility = Visibility.Visible; 

{% endhighlight %}

Additionally, you need to set label for each series using [`ChartSeries.Label`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~Label.html) property, which will be displayed in corresponding legend.

{% highlight C# %} 

series.Label = "Heights";

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/legend) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) to customize legend.

## Enable tooltip

Tooltips are used to show information about the segment, when you tap on the segment. You can enable tooltip by setting [`ChartSeries.TooltipEnabled `](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~TooltipEnabled.html) property to true.

{% highlight C# %} 

series.TooltipEnabled = true;

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/tooltip) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) to customize tooltip.

The following code example gives you the complete code of above configurations.

{% highlight C# %} 

using Com.Syncfusion.Charts;

namespace Chart_GettingStarted
{
    [Activity( MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);

            SfChart chart = new SfChart(this);
            chart.Title.Text = "Chart";
            chart.SetBackgroundColor(Color.White);
	
			//Initializing view model
			ViewModel model = new ViewModel();

            //Initializing primary axis
            CategoryAxis primaryAxis = new CategoryAxis();
            primaryAxis.Title.Text = "Name";
            chart.PrimaryAxis = primaryAxis;

            //Initializing secondary Axis
            NumericalAxis secondaryAxis = new NumericalAxis();
            secondaryAxis.Title.Text = "Height (in cm)";
            chart.SecondaryAxis = secondaryAxis;

            //Initializing column series
            ColumnSeries series = new ColumnSeries();
            series.ItemsSource = viewModel.Data;
            series.XBindingPath = "Name";
            series.YBindingPath = "Height";
          
            series.DataMarker.ShowLabel = true;
            series.Label = "Heights";
            series.TooltipEnabled = true;

            chart.Series.Add(series);
            chart.Legend.Visibility = Visibility.Visible;    
            SetContentView(chart);
        }
    }
}

{% endhighlight %}

The following chart is created as a result of the above codes.

![Tooltip support in Xamarin.Android Chart](Getting-Started_images/img2.png)

You can find the complete getting started sample from this [link.](http://files2.syncfusion.com/Xamarin.Android/Samples/Chart_GettingStarted.zip)
