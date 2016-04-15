---
layout: post
title: Chart Animation
description: How to enable animation in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Animation

`SfChart` provides animation support for data series. Series will be animated whenever the DataSource changes. Animation can be enabled by using the `AnimationEnabled` method. You can also control the duration of the animation using `AnimationDuration` method. 

{% highlight c# %}
[C#]

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.DataSource = dataPoints;

columnSeries.AnimationEnabled = true;

columnSeries.AnimationDuration = 2;

{% endhighlight %}