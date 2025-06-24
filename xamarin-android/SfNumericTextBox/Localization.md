---
layout: post
title: Localization in Syncfusion® NumericTextBox Control for Xamarin.Android
description: Learn how to localize the NumericTextBox control for different cultures and regions.
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---
# Localization

The SfNumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with a `System.Globalization.CultureInfo` object instance.

N> The default `Culture` property value is en-US.

{% tabs %}

{% highlight c# %}

	numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
	
{% endhighlight %}

{% endtabs %}

![NumericTextBox with French localization](images/Culture.png)
