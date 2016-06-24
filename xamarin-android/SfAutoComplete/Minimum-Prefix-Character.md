---
layout : post
title : MinimumPrefixCharacters for Syncfusion AutoComplete Control in Xamarin.Android
description : Learn how to set the MinimumPrefixCharacter in AutoComplete 
platform : Xamarin.Android
control : AutoComplete
documentation : ug
---

# MinimumPrefixCharacter

* The minimum number of characters to be entered in the text box before the autocomplete suggestion box displays possible matches.

N> Population of the Autocomplete Box does not occur until the conditions specified by the MinimumPrefixCharacter property values are met.The default is 1.

{% highlight C# %}
	
	countryAutoComplete.MinimumPrefixCharacters = 4;
	 
{% endhighlight %}
	
![](images/minimumprefixcharacter.png)
