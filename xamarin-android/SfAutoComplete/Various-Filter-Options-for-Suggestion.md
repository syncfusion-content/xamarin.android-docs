---
layout: post
title: Syncfusion® AutoComplete Filter Options for Suggestion
description: Learn how to configure various filter options and suggestion modes in SfAutoComplete
platform: xamarin.android
control: SfAutoComplete
documentation: ug
---

# Various Filter Options for Suggestion

By default, items that match the starting letter will be displayed as suggestions. This behavior can be changed using the `SuggestionMode` property, which provides various options to filter the data according to the text entered. There are eight types of suggestion modes, which are described as follows:

## Words that Start with Input Text

Displays the list of suggestions based on the starting letter.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith filter mode example](images/startswith.png)
### Filter with Character Casing

Displays the list of suggestions based on the starting letter with case sensitivity.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![StartsWith case sensitive filter mode example](images/startswithcasesensitive.png)
## Words that Contain the Input Text

Displays the list of suggestions if the AutoComplete list contains those words.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains filter mode example](images/contains.png)
### Filter with Character Casing

Displays the list of suggestions if the AutoComplete list contains those words with case sensitivity.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Contains case sensitive filter mode example](images/containswithcasesensitive.png)
## Words that Equal the Input Text

Displays words that exactly match the input text.
{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals filter mode example](images/equals.png)
### Filter with Character Casing

Displays words that exactly match the input text with case sensitivity.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![Equals case sensitive filter mode example](images/equalswithcasesensitive.png)
## Words that End with Input Text

Displays the list of suggestions based on the ending text.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith filter mode example](images/endswith.png)
### Filter with Character Casing

Displays the list of suggestions based on the ending text with case sensitivity.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![EndsWith case sensitive filter mode example](images/endswithcasesensitive.png)
## Custom Filter

Displays the list of suggestions based on custom filtering logic in the SfAutoComplete.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.SuggestionMode = SuggestionMode.Custom;
	 
{% endhighlight %}

{% endtabs %}
	
![Custom filter mode example](images/customfilter.png)
