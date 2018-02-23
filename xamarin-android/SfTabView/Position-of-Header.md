---
layout: post
title: Positioning of header 
description: Positioning of header in Syncfusion TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

## Positioning of header

Tab headers can be positioned either above the content or below the content. This can be done by setting the `TabHeaderPosition` property of `SfTabView`.

{% tabs %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When the header is not needed, set the `DisplayMode` of `SfTabView` to `NoHeader`.
