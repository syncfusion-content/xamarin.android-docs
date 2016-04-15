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

## Animation Supported Series

<table>
<tr>
<th>
Series<br/><br/></th><th>
iOS<br/><br/></th><th>
Android<br/><br/></th><th>
WP<br/><br/></th></tr>
<tr>
<td>
Line<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
StepLine<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Spline<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Column<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Bar<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Area<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
SplineArea<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Pie<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Doughnut<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Pyramid<br/><br/></td><td>
No<br/><br/></td><td>
No<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Funnel<br/><br/></td><td>
No<br/><br/></td><td>
No<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Bubble<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
Scatter<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
RangeColumn<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Candle<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
OHLC<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Polar<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
Radar<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
StackedColumn<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
StackedColumn100<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
StackedBar<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
StackedBar100<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
<tr>
<td>
StackedArea<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td></tr>
<tr>
<td>
StackedArea100<br/><br/></td><td>
Yes<br/><br/></td><td>
Yes<br/><br/></td><td>
No<br/><br/></td></tr>
</table>