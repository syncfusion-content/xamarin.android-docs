---
layout : post
title: Suggestion Display Mode in Xamarin.Android SfAutoComplete Control | Syncfusion®
description: Learn here about Suggestion Display Mode in Syncfusion® Essential® Xamarin.Android SfAutoComplete Control, its elements, and more.
platform: Xamarin.Android
control: SfAutoComplete
documentation: ug
---

# Suggestion Display Mode in Xamarin.Android SfAutoComplete

The `AutoCompleteMode` property is used to determine the suggestion pattern for displaying the filtered data according to the text entered. The different types of patterns are described below:

* Suggest

* Append

* Suggest and Append

N> The default mode is Suggest.

## Append

Appends the first matching string to the entered text.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}

{% endtabs %}
	
## Suggest in Dropdown 

Displays suggestions in the dropdown.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}

## Suggest and Append

Displays suggestions in the dropdown and appends the first matching string to the entered text.
{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
	 
{% endhighlight %}

{% endtabs %}

![Xamarin.Android SfAutoComplete autocomplete mode](images/autocompletemode.png)
 

