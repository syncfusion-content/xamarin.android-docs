---
layout: post
title: Chart Animation
description: How to enable animation in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Animation

[`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) provides animation support for data series. Series will be animated whenever the DataSource changes. Animation can be enabled by using the [`AnimationEnabled`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~AnimationEnabled.html) property. You can also control the duration of the animation using [`AnimationDuration`](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfchart/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartSeries~AnimationDuration.html) property. 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.DataSource = dataPoints;

columnSeries.AnimationEnabled = true;

columnSeries.AnimationDuration = 2;

{% endhighlight %}