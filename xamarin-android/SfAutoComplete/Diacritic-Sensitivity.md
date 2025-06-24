---
layout : post
title : Diacritic Sensitivity in Syncfusion® SfAutoComplete Control for Xamarin.Android
description : Learn how to enable and disable diacritic sensitivity in SfAutoComplete for multilingual text search
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Diacritic Sensitivity

The control supports multiple keyboard types, allowing you to populate items from languages with diacritical marks and search for them using English characters from an en-US keyboard. Users can enable or disable diacritic sensitivity using the `IgnoreDiacritic` property.

The following code example demonstrates how to disable diacritic sensitivity so that items in the suggestion list are populated when entering any diacritic character of that alphabet.


{% tabs %}

{% highlight C# %}

List<String> diacritic = new List<String>(); 
diacritic.Add("Hów tó gâin wéight?");
diacritic.Add("Hów tó drâw ân éléphânt?");
diacritic.Add("Whéré cân I buy â câmérâ?");
diacritic.Add("Guidé mé âll thé wây");
diacritic.Add("Hów tó mâké â câké?");
diacritic.Add("Sây, Hélló Wórld!");
diacritic.Add("Hów tó mâké â róbót?");
diacritic.Add("Whât timé nów in Indiâ?");

ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, diacritic);
countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
countryAutoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
countryNameAutoComplete.HighlightedTextColor = Color.Red; 
countryAutoComplete.IgnoreDiacritic=false;
	 
{% endhighlight %}

{% endtabs %}
	
![Diacritic sensitivity example](images/diacritic.png)
