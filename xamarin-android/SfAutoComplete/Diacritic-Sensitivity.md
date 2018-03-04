---
layout : post
title : Diacritic sensitivity in Syncfusion SfAutoComplete control for Xamarin.Android
description : Learn how to enable and disable Diacritic sensitivity in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the `IgnoreDiacritic` porperty. In the below code example we have illustrate how to disable the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.


{% tabs %}

{% highlight C# %}
	
	List<String> diacritic = new List<String>(); 
	    diacritic.Add("Diréct mé tó hómé");
		diacritic.Add("Hów tó gâin wéight?");
		diacritic.Add("Hów tó drâw ân éléphânt?");
		diacritic.Add("Whéré cân I buy â câmérâ?");
		diacritic.Add("Guidé mé âll thé wây");
		diacritic.Add("Hów tó mâké â câké?");
		diacritic.Add("Sây, Hélló Wórld!");
		diacritic.Add("Hów tó mâké â róbót?");
		diacritic.Add("Whât timé nów in Indiâ?");
		diacritic.Add("Whó is whó in thé wórld?");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, diacritic);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.MaximumSuggestion="2";
	countryAutoComplete.IgnoreDiacritic=false;;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/diacritic.png)


	