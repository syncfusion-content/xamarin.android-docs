---
layout: post
title: Selection Indicator in Xamarin.Android TabView Control | Syncfusion®
description: Learn here about Selection Indicator in Syncfusion® Essential® Xamarin.Android TabView Control, its elements, and more.
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Selection Indicator strip in Xamarin.Android TabView

Selection indicator strip can be used to indicate the selected index of the tab view control. It can be customized with the built in APIs available in `SelectionIndicatorSettings` of `SfTabView`.

![Xamarin.Android TabView Selection Indicator](images/Selection-Indicator/xamarin_android_tabstyle02.png)


Selection indicator can be positioned below the title or above the title or else it can be filled in the entire selected header space.

{% tabs %}

{% highlight C# %}

var selectionIndicatorSettings = new SelectionIndicatorSettings();
selectionIndicatorSettings.Color = Color.Yellow;
selectionIndicatorSettings.Position = SelectionIndicatorPosition.Top;
selectionIndicatorSettings.StrokeThickness = 10;

tabView.SelectionIndicatorSettings = selectionIndicatorSettings;

			
{% endhighlight %}

{% endtabs %}

N> Stroke thickness is not applicable when selection indicator’s position is set as Fill.

