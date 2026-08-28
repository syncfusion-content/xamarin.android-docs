---
layout: post
title: ComboBoxMode for Syncfusion® ComboBox control in Xamarin.Android
description: Learn how to configure the ComboBoxMode property in SfComboBox to control suggestion display patterns
platform: xamarin.android
control: SfComboBox
documentation: ug
---

# Suggestion Display Mode

The `ComboBoxMode` property determines how filtered suggestions are displayed based on the text entered by the user. The available display modes are described below:
* Suggest

* Append
* SuggestAppend

N> The default mode is Suggest.

## Suggest Mode

The Suggest mode displays filtered suggestions in a drop-down list below the ComboBox.
{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.Suggest;	

{% endhighlight %}

{% endtabs %}

## Append Mode

The Append mode automatically appends the first matching string to the entered text, allowing users to see potential completions inline.
{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.Append;

{% endhighlight %}

{% endtabs %}

## SuggestAppend Mode

The SuggestAppend mode combines both approaches by displaying suggestions in a drop-down list while simultaneously appending the first matching string to the entered text.
{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![ComboBox modes demonstration](images/comboboxmode.png)
