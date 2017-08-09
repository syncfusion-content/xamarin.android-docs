---
layout: post
title: Chart Animation
description: How to enable animation in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Animation

SfChart provides animation support for data series. Series will be animated whenever the ItemsSource changes. Animation can be enabled by using the [`EnableAnimation`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~AnimationEnabled.html) property. You can also control the duration of the animation using [`AnimationDuration`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~AnimationDuration.html) property. 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.ItemsSource = dataPoints;

columnSeries.XBindingPath = "XValue";

columnSeries.YBindingPath = "YValue";

columnSeries.EnableAnimation = true;

columnSeries.AnimationDuration = 2;

{% endhighlight %}