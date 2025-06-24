---
layout: post
title: Populating Items in Xamarin.Android SfAutoComplete Control | Syncfusion®
description: Learn here about Populating Items in Syncfusion® Essential® Xamarin.Android SfAutoComplete Control, its elements, and more.
platform: Xamarin.Android
control: SfAutoComplete
documentation: ug
---

# Populating Items in Xamarin.Android SfAutoComplete

The `AutoCompleteSource` property in the SfAutoComplete control is used to set the list of strings for the suggestion dropdown using a DataAdapter.

The AutoComplete functionality creates a text input that automatically completes input strings by comparing the entered prefix to the prefixes of all strings in the data source. This is useful for text input controls where URLs, addresses, file names, or commands are frequently entered.

Setting the AutoCompleteSource is optional, but it must be configured to use custom data sources with the `AutoCompleteCustomSource` property.

{% tabs %}

{% highlight C# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Afghanistan");
	countryList.Add ("Akrotiri");
	countryList.Add ("Albania");
	countryList.Add ("Algeria");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.AutoCompleteMode=AutoCompleteMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}
	
![Xamarin.Android SfAutoComplete AutoComplete Source](images/autocompletesource.png)

