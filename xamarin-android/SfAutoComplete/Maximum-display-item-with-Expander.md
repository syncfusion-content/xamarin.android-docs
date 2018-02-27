---
layout : post
title : LoadMore in Syncfusion SfAutoComplete control for Xamarin.Android
description : Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Maximum Display Item with Expander

Restrict the number of suggestions displayed and have the remaining items loaded by selecting LoadMore. We can also set the maximum suggestion to be displayed using LoadMore method.

{% tabs %}

{% highlight C# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Afghanistan");
	countryList.Add ("Akrotiri");
	countryList.Add ("Albania");
	countryList.Add ("Algeria");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.MaximumSuggestion="2";
	 
{% endhighlight %}

{% endtabs %}
	
![](images/loadmore.png)

