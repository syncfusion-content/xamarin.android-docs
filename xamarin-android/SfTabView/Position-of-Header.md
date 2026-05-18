---
layout: post
title: Positioning of Header
description: Positioning of header in Syncfusion® TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Positioning of Header

Tab headers can be positioned either above the content or below the content, it can be done by setting TabHeaderPosition property of SfTabView.

{% tabs %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When header is not needed we can set `DisplayMode` of `SfTabView` as `NoHeader`.
