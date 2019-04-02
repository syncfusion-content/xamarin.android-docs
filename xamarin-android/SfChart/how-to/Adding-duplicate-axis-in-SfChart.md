---
layout: post
title: Adding duplicate axis in Syncfusion SfChart
description: Adding duplicate axis in SfChart
platform: Android
control: Chart
documentation: ug
---

##  Adding duplicate axis in SfChart

Duplicate axis can be added in the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) using the chart [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection property. The axis added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection will be aligned to the horizontal position by default. The axis position can be changed by using the [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~IsVertical.html) bool property of [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis.html). When the [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis~IsVertical.html) property is set true, the axis will be placed vertically and vice versa.

N> 
- The [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartAxis.html) added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection will not be removed until removing it from the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection. 
- The [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection does not support the clear method. 
- Same axis can't be added more than once in [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html); only distinct axis will be added to the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartBase~Axes.html) collection.