---
layout: post
title: Suggestion mode for Syncfusion® ComboBox Control in Xamarin.Android
description: Learn how to configure various filtering modes and suggestion display options in SfComboBox
platform: Xamarin.Android
control: SfComboBox
documentation: ug
---

# Various Filter Options for Suggestions

The SfComboBox provides filtering options to filter suggestions in the dropdown list.

{% tabs %}

{% highlight C# %}
comboBox.AllowFiltering = true;
comboBox.IsEditableMode = true;	 
{% endhighlight %}

{% endtabs %}

## Types of Filtering

String comparison for filtering suggestions can be configured using the `SuggestionMode` property. The default filtering strategy is `StartsWith`, and it is case insensitive. The available filtering modes are:

* StartsWith
* StartsWithCaseSensitive
* Contains
* ContainsWithCaseSensitive
* Equals
* EqualsWithCaseSensitive
* EndsWith
* EndsWithCaseSensitive
* Custom

## StartsWith Mode
### Words that Start with Input Text

Displays suggestions based on items that begin with the entered characters.
{% tabs %}

{% highlight C# %}

    comboBox.SuggestionMode = SuggestionMode.StartsWith;   	
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith filtering mode](images/startswith.png)

### Case-Sensitive StartsWith

Displays suggestions based on items that begin with the entered characters, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith case-sensitive filtering mode](images/startswithcasesensitive.png)

## Contains Mode
### Words that Contain the Input Text

Displays suggestions for items that contain the entered text anywhere within the string.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains filtering mode](images/contains.png)

### Case-Sensitive Contains

Displays suggestions for items that contain the entered text with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains case-sensitive filtering mode](images/containswithcasesensitive.png)

## Equals Mode
### Words that Equal the Input Text

Displays suggestions for items that exactly match the entered text.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals filtering mode](images/equals.png)

### Case-Sensitive Equals

Displays suggestions for items that exactly match the entered text with case-sensitive comparison.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals case-sensitive filtering mode](images/equalswithcasesensitive.png)

## EndsWith Mode
### Words that End with Input Text

Displays suggestions based on items that end with the entered characters.
{% tabs %}

{% highlight C# %}
	
	comboBox.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith filtering mode](images/endswith.png)

### Case-Sensitive EndsWith

Displays suggestions based on items that end with the entered characters, with case-sensitive matching.
{% tabs %}

{% highlight C# %}
	
comboBox.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith case-sensitive filtering mode](images/endswithcasesensitive.png)

## Custom Filter Mode

The Custom mode allows you to implement custom filtering logic by handling the filtering events or providing custom filter predicates.
{% tabs %}

{% highlight C# %}
	
comboBox.SuggestionMode = SuggestionMode.Custom;
	 
{% endhighlight %}

{% endtabs %}
	
![Custom filtering mode](images/customfilter.png)
