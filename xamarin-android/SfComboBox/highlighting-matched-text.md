---
layout: post
title: Text Highlighting in Syncfusion® SfComboBox control for Xamarin.Android
description: Learn how to highlight matching text in the SfComboBox dropdown list to improve user experience and make item selection more intuitive with customizable highlighting options.
platform: Xamarin.Android
control: SfComboBox
documentation: ug
---

# Highlighting matched text

An item can be picked with more clarity by highlight the matching characters in a suggestion list using the following two ways:

* First occurrence

* Multiple occurrence

Highlighting the text can be indicated with various customizing styles by enabling the following properties:

* `HighlightedTextColor` - sets the color of the highlighted text for differentiating the highlighted characters.

* `HighlightedTextFontTypeFace` - sets the FontAttributes of the highlighted text.

N> The drop-down text can be highlighted only when the AllowFiltering is set to true.

## First occurrence

Highlights the first position of the matching characters in the suggestion list.

{% tabs %}

{% highlight C# %}

comboBox.AllowFiltering = true;
comboBox.IsEditableMode = true;
comboBox.TextHighlightMode = OccurrenceMode.FirstOccurrence;
comboBox.HighlightedTextColor = Color.Red;
comboBox.HighlightedTextFontTypeFace = TypefaceStyle.Bold; 
	 
{% endhighlight %}

{% endtabs %}

![SfComboBox with first occurrence text highlighting](images/FirstOccurrence.png)

## Multiple Occurrence Highlighting

This mode highlights all occurrences of matching characters throughout each item in the dropdown list. It works particularly well with the `Contains` suggestion mode to provide comprehensive text matching.
{% tabs %}

{% highlight C# %}

comboBox.AllowFiltering = true;
comboBox.IsEditableMode = true;
comboBox.TextHighlightMode = OccurrenceMode.MultipleOccurrence;
comboBox.HighlightedTextColor = Color.Red;
comboBox.HighlightedTextFontTypeFace = TypefaceStyle.Bold;
comboBox.SuggestionMode = SuggestionMode.Contains; 
	 
{% endhighlight %}

{% endtabs %}
	
![SfComboBox with multiple occurrence text highlighting](images/MultipleOccurrence.png)

