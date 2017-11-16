---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Android
description : A quick tour to initial users on Syncfusion SfAutoComplete control for Xamarin.Android platform 
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a SfAutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in SfAutoComplete control.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfAutoComplete.Android.dll

### Add SfAutoComplete

The following steps helps to add a SfAutoComplete control through code.

* Adding namespace for the added assemblies.

{% tabs %}

{% highlight C# %}

using Com.Syncfusion.Autocomplete; 

{% endhighlight %}

{% endtabs %}

* Now add the SfAutoComplete control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

            LinearLayout linearlayout = new LinearLayout(this);
            linearlayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
            linearlayout.SetBackgroundColor(Android.Graphics.Color.Black);

            SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
            countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);
            linearlayout.AddView(countryAutoComplete);
            SetContentView(linearlayout);
	
{% endhighlight %}

{% endtabs %}

	
## Add Items

A list of string with country names are created and added to auto complete source. This list will be populated as suggestion list by setting the `AutoCompleteSource` property based on text entry .

You can set the suggestion list to the SfAutoComplete using the property `AutoCompleteSource`. Add the AutoCompleteSource for the SfAutoComplete as follows.

{% tabs %}

{% highlight C# %}

            LinearLayout linearlayout = new LinearLayout(this);
            linearlayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
            linearlayout.SetBackgroundColor(Android.Graphics.Color.Black);

            SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
            countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

            List<String> countryList = new List<String>();
            countryList.Add("Uganda");
            countryList.Add("Ukraine");
            countryList.Add("United Arab Emirates");
            countryList.Add("United Kingdom");
            countryList.Add("United States");
            ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
            countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
            countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;

            linearlayout.AddView(countryAutoComplete);
            SetContentView(linearlayout);

{% endhighlight %}

{% endtabs %}

## Set Filter Mode

Filters can be applied to the displayed items based on starting letter. We can also append the first item from the suggested list to the TextBox. This can be done by using the `SuggestionMode` and `AutoCompleteMode` properties in SfAutoComplete control.

The following example shows the SfAutoComplete control which suggest the country list starting with the letter U.

{% tabs %}

{% highlight C# %}

            LinearLayout linearlayout = new LinearLayout(this);
            linearlayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
            linearlayout.SetBackgroundColor(Android.Graphics.Color.Black);

            SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
            countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

            List<String> countryList = new List<String>();
            countryList.Add("Uganda");
            countryList.Add("Ukraine");
            countryList.Add("United Arab Emirates");
            countryList.Add("United Kingdom");
            countryList.Add("United States");
            ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
            countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);

            countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
            countryAutoComplete.MaximumDropDownHeight = 200;
            countryAutoComplete.Watermark = "Enter a country name";
            countryAutoComplete.PopUpDelay = 100;
            countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;

            linearLayout.AddView(countryAutoComplete);
            SetContentView(linearLayout);

	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)

## AXML code to set Layout

Using Android's XML codes, we can quickly design UI layouts in Xamarin.Android.

Each layout file must contain exactly one root element, which must be a View or ViewGroup object. Once we have defined the root element, we can add additional layout objects as child elements to gradually build a View hierarchy that defines the layout.

In Main.XML page enter the below codes.

{% tabs %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"> 

    <com.syncfusion.autocomplete.SfAutoComplete
        android:layout_width="300dp"
        android:layout_height="40dp"
        android:id="@+id/autocomplete" />
</LinearLayout>
	
{% endtabs %}

In MainActivity.cs page enter the below given code to get the instance of our control. Also we can use any of the property related to SfAutoComplete control here.

{% tabs %}

SfAutoComplete auto = FindViewById<SfAutoComplete>(Resource.Id.autocomplete);

auto.Text = "AutoComplete";

{% endtabs %}