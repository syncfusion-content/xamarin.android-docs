---
layout: post
title: Performance tips
description: How to improve the performance of Essential Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Performance

When there are large number of points to load in line series, you can use `FastLineSeries` series instead of `LineSeries`. To renderer a fast line chart, create an instance of `FastLineSeries` and add to the series using `Series` property of `SfChart`.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries();
fastLineSeries.DataSource = Data;

chart.Series.Add(fastLineSeries);

{% endhighlight %}

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** to view the point information.