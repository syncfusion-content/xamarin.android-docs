---
layout: post
title: Localization in Syncfusion® NumericUpDown Control for Xamarin.Android
description: Learn how to localize the NumericUpDown control to support different cultures and regions.
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
keywords: NumericUpDown, localization, culture, globalization, regional settings, formatting
---
# Localization

The `SfNumericUpDown` control supports localization to display values according to specific cultural conventions. You can localize the control by setting the `Culture` property with a `System.Globalization.CultureInfo` object instance.

N> The default `Culture` property value is `en-US`.

{% tabs %}

{% highlight C# %}

	numeric.Culture = new System.Globalization.CultureInfo("en-US");
	
{% endhighlight %}

{% endtabs %}

![](images/Culture.png)




