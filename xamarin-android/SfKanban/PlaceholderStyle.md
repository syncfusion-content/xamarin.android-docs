---
layout: post
title: PlaceholderStyle for Xamarin.Android Kanban
description: Kanban Placeholder style
platform: Xamarin.Android
control: Kanban
documentation: ug
---

# Placeholder

The placeholder is to denote a card's new position in the [`KanbanColumn`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanColumn.html). It will appear while dragging a card over the column.

### Placeholder style

[`PlaceholderStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~PlaceholderStyle.html) property is used to customize the placeholder. Following [`KanbanPlaceholderStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html) properties are used to customize its appearance.

* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~BackgroundColor.html) - This property is used to change the background color of the placeholder.
* [`DashGap`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~DashGap.html) - This property is used to determine the dash gap of the placeholder.
* [`DashWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~DashWidth.html) - This property is used to provide dash width of the placeholder.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~StrokeColor.html) - This property is used to change the stroke color of the placeholder.
* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~StrokeWidth.html) - This property is used to change the stroke width of the placeholder.
* [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~TextSize.html) - This property is used to change the text size of the placeholder.
* [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~TextColor.html) - This property is used to change the text color of the placeholder.

Following properties are used to customize the selected category when you have more than one category in a column.

* [`SelectedBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedBackgroundColor.html) - This property is used to change the background color of the selected placeholder.
* [`SelectedDashGap`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedDashGap.html) - This property is used to determine the dash gap of the selected placeholder.
* [`SelectedDashWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedDashWidth.html) - This property is used to provide dash width of the selected placeholder.
* [`SelectedStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedStrokeColor.html) - This property is used to change the stroke color of the selected placeholder.
* [`SelectedStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedStrokeWidth.html) - This property is used to change the stroke width of the selected placeholder.
* [`SelectedTextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedTextSize.html) - This property is used to change the size of the text in selected placeholder.
* [`SelectedTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanPlaceholderStyle~SelectedTextColor.html) - This property is used to change the color of the text in selected placeholder.

The following code example describes the above behavior.

{% highlight C# %}

KanbanPlaceholderStyle style = new KanbanPlaceholderStyle();
style.BackgroundColor = Color.Rgb(239, 89, 123);
style.DashGap = 1;
style.DashWidth = 1;
style.StrokeColor = Color.Blue;
style.StrokeWidth = 2;
style.TextSize = 20;
style.TextColor = Color.Red;

style.SelectedBackgroundColor = Color.Rgb(239, 89, 123);
style.SelectedDashGap = 2;
style.SelectedDashWidth = 1;
style.SelectedStrokeColor = Color.Yellow;
style.SelectedStrokeWidth = 2;
style.SelectedTextSize = 20;
style.SelectedTextColor = Color.Green;

kanban.PlaceholderStyle = style;

{% endhighlight %}
