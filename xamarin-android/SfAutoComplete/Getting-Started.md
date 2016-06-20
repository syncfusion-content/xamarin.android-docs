---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Android
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.Android platform 
platform : Xamarin.Android
control : AutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a AutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in AutoComplete control.

![](images/gettingstarted.png)

## Creating your first AutoComplete in Xamarin.Android

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfAutoComplete.Andriod.dll

### Add and configure the AutoComplete Control

The following steps explain on how to create an AutoComplete and configure its elements,

* Adding reference to autocomplete.

{% highlight C# %}

	using Com.Syncfusion.Autocomplete; 

{% endhighlight %}


* Create an instance of AutoComplete.

{% highlight C# %}

	SfAutoComplete countryAutoComplete = new SfAutoComplete(con);
	SetContentView(countryAutoComplete);
	
{% endhighlight %}

	
### Add the AutoCompleteSource for AutoComplete.

You can set the suggestion list to the AutoComplete using the property AutoCompleteSource.   Add the AutoCompleteSource for the AutoComplete as follows.

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

### Customization of AutoComplete Properties

You can set the behavior of suggestions by adding AutoCompleteMode to Autocomplete.

{% highlight C# %}

	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.MaximumDropDownHeight = 200;
	countryAutoComplete.Watermark = "Enter a country name";
	countryAutoComplete.PopUpDelay = 100;
	countryAutoComplete.AutoCompleteMode=AutoCompleteMode.Append;
	countryAutoComplete.MinimumPrefixCharacters = 2;
	
{% endhighlight %}

