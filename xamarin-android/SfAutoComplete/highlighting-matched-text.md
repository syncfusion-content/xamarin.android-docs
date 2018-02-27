---
layout : post
title : MatchHighlighting in Syncfusion SfAutoComplete control for Xamarin.Android
description : Learn how to highlight the matched text in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Highlighting matched text

Highlight matching characters in a suggestion list to pick an item with more clarity. There are two ways to highlight the matching text:


* FirstOccurrence

* MultipleOccurrence

## FirstOccurrence

{% tabs %}

{% highlight C# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Afghanistan");
	countryList.Add ("Akrotiri");
	countryList.Add ("Albania");
	countryList.Add ("Algeria");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
	countryAutoComplete.TextHighlightMode=OccurrenceMode.FirstOccurrence;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/FirstOccurrence.png)

## MultipleOccurrence

{% tabs %}

{% highlight C# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Afghanistan");
	countryList.Add ("Akrotiri");
	countryList.Add ("Albania");
	countryList.Add ("Algeria");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.SuggestionMode=SuggestionMode.Contains;
	countryAutoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/MultipleOccurrence.png)



