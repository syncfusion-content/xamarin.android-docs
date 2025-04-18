---
layout : post
title: AutoComplete mode in Xamarin.Android SfAutoComplete Control|Syncfusion®
description: Learn here about Suggestion Display Mode in Syncfusion® Essential® Xamarin.Android SfAutoComplete Control, its elements, and more.
platform: Xamarin.Android
control: SfAutoComplete
documentation: ug
---

# Suggestion Display Mode in Xamarin.Android SfAutoComplete

The `AutocompleteMode` property is used to decide the suggestion pattern for displaying the filtered data according to the text entered. The different types of pattern are described below

* Suggest

* Append

* Suggest and Append

N> The default option is suggest mode.

## Append

* Append - It appends the first matching string with the entered character.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}

{% endtabs %}
	
## Suggest in Dropdown 

* Suggest - It displays the suggestion in the dropdown.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}

## Both Append and Suggest in DropDown
	
* SuggestAppend - It displays the suggestion in the dropdown along with appending the first matching string.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
	 
{% endhighlight %}

{% endtabs %}

![Xamarin.Android SfAutoComplete autocomplete mode](images/autocompletemode.png)
 
