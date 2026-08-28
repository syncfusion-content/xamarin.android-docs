---
layout: post
title: Highlighting Matched Text in Syncfusion® SfAutoComplete Control
description: Learn how to highlight matched text in SfAutoComplete for Xamarin.Android and understand how to highlight matching characters in the suggestion list
platform: xamarin.android
control: SfAutoComplete
documentation: ug
---

# Highlighting Matched Text

Highlight matching characters in a suggestion list to pick an item with more clarity. There are two ways to highlight the matching text:


* First Occurrence

* Multiple Occurrence

Text highlighting can be customized with various styles using the following properties:

* `HighlightedTextColor` - Sets the color of the highlighted text for differentiating the highlighted characters.
* `HighlightedTextFontTypeFace` - Sets the font attributes of the highlighted text.

## First Occurrence

This mode highlights the first position of the matching characters in the suggestion list.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
countryAutoComplete.TextHighlightMode = OccurrenceMode.FirstOccurrence; 
countryAutoComplete.HighlightedTextColor = Color.Blue; 
countryAutoComplete.HighlightedTextFontTypeFace = TypefaceStyle.Bold; 
	 
{% endhighlight %}

{% endtabs %}

N> The default color of `HighlightedTextColor` is Red. The default font attribute of `HighlightedTextFontTypeFace` is None.
![First Occurrence AutoComplete Image](images/FirstOccurrence.png)

## Multiple Occurrence

This mode highlights the matching characters that are present everywhere in the suggestion list for Contains case in SuggestionMode.

{% tabs %}

{% highlight C# %}

countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
countryAutoComplete.TextHighlightMode = OccurrenceMode.MultipleOccurrence;
countryNameAutoComplete.HighlightedTextColor = Color.Red; 
countryNameAutoComplete.HighlightedTextFontTypeFace = TypefaceStyle.Bold;
	 
{% endhighlight %}

{% endtabs %}
	
![Multiple Occurrence AutoComplete Image](images/MultipleOccurrence.png)




