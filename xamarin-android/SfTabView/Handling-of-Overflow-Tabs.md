---
layout: post
title: Handling Overflow Tabs
description: Handling of overflow tabs in Syncfusion® TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Handling overflow tabs

When you have a large number of tabs in your TabView, the control needs to manage tabs that don't fit within the available header space. By default, a scroller will be enabled to view the overflow headers. If needed, you can change this behavior to display overflow tabs in a dropdown by setting the `OverflowMode` property of `SfTabView` to `DropDown`.
{% tabs %}

{% highlight C# %}

tabView.OverflowMode = OverflowMode.DropDown;
			
{% endhighlight %}

{% endtabs %}

## DropDown Mode
By selecting the dropdown option for the TabView control, a button called "Overflow button" (or "More button") will be added to the header. When you click on this button, it will display a popup to navigate to the other tab indices.

N> The popup will display text values only. It will show the title value of the respective tab item.

## How to customize the more button?

The appearance of the overflow button can be customized through the `OverflowButtonSettings` property of `SfTabView`. This property provides APIs to customize both text and font icons for the button.

{% tabs %}

{% highlight C# %}

var overflowButtonSettings = new OverflowButtonSettings();
overflowButtonSettings.BackgroundColor = Color.Red;
overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
overflowButtonSettings.Title = "...";
overflowButtonSettings.TitleFontSize = 30;
overflowButtonSettings.TitleFontColor = Color.Yellow;
tabView.OverflowButtonSettings = overflowButtonSettings;
			
{% endhighlight %}

{% endtabs %}

