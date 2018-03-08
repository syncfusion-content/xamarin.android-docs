---
layout : post
title : Header and Footer in Syncfusion SfAutoComplete control for Xamarin.Android
description :  Learn how to enable Header and Footer in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

## Header and Footer

We can provide Header and Footer content in the SfAutoComplete by enabling `ShowDropDownHeaderView` and `ShowDropDownFooterView`. 

## Header Content

We can provide Header Content at the top of the AutoComplete's Suggestion box. `DropDownHeaderView` property is used to set the content of the header. The following code example illustrate how to set Header content in SfAutoComplete. The height of the Header in the SfAutoComplete can be adjusted by the property `DropDownHeaderViewHeight`.

{% tabs %}

{% highlight C# %}
	
<<<<<<< HEAD
List<String> countryList = new List<String>();
countryList.Add("Uganda");
countryList.Add("Ukraine");
countryList.Add("United Arab Emirates");
countryList.Add("United Kingdom");
countryList.Add("United States");
ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
// Set the height of the Header View
countryAutoComplete.DropDownHeaderViewHeight = 50;
countryAutoComplete.ShowDropDownHeaderView = true;

TextView textView = new TextView(this);
textView.Text = "Search For U";
textView.SetBackgroundColor(Color.LightGray);
textView.Gravity = GravityFlags.CenterVertical;
textView.SetTextColor(Color.ParseColor("Blue"));
textView.TextSize = 16;
textView.SetPadding(20, 0, 20, 0);
countryAutoComplete.DropDownHeaderView = textView;
=======
	List<String> countryList = new List<String>(); 
	countryList.Add ("Uganda");
	countryList.Add ("Ukraine");
	countryList.Add ("United Arab Emirates");
	countryList.Add ("United Kingdom");
	countryList.Add ("United States");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
	countryAutoComplete.ShowDropDownHeaderView=true;

    TextView textView = new TextView(context);
    textView.Text = "Search for U"
	textView.setTextColor(Color.parseColor("Blue"));
    textView.TextSize = 16;
    textView.SetPadding(20, 0, 20, 0);
	countryAutoComplete.DropDownHeaderView=textView;


>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
	 
{% endhighlight %}

{% endtabs %}
<<<<<<< HEAD
=======
	
## Header Height

The height of the Header in the SfAutoComplete can be adjusted by the property `DropDownHeaderViewHeight`.

{% tabs %}

{% highlight C# %}
List<String> countryList = new List<String>(); 
	countryList.Add ("Uganda");
	countryList.Add ("Ukraine");
	countryList.Add ("United Arab Emirates");
	countryList.Add ("United Kingdom");
	countryList.Add ("United States");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.SuggestionMode=SuggestionMode.StartsWith;
	countryAutoComplete.
	
	//Set the Height of the Header View 

	DropDownHeaderViewHeight=50;
	countryAutoComplete.ShowDropDownHeaderView=true;

	 TextView textView = new TextView(context);
     textView.Text = "Search for U"
	 textView.setTextColor(Color.parseColor("Blue"));
     textView.TextSize = 20;
     textView.SetPadding(20, 0, 20, 0);
	countryAutoComplete.DropDownHeaderView=textView;

{% endhighlight %}

{% endtabs %}
	
>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a

![](images/Header.png)

## Footer Content

We can provide Footer Content at the bottom of the AutoComplete's Suggestion box. `DropDownFooterView` property is used to set the content of the footer. The following code example illustrate how to set Footer content in SfAutoComplete. The height of the Footer in the SfAutoComplete can be adjusted by the property `DropDownFooterViewHeight`.

{% tabs %}

{% highlight C# %}
	
<<<<<<< HEAD
List<String> countryList = new List<String>();
countryList.Add("Uganda");
countryList.Add("Ukraine");
countryList.Add("United Arab Emirates");
countryList.Add("United Kingdom");
countryList.Add("United States");
ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
countryAutoComplete.ShowDropDownHeaderView = true;

// set the Height of the FooterView
countryAutoComplete.DropDownFooterViewHeight = 50;
TextView textView = new TextView(this);
textView.Text = "Add New";
textView.SetBackgroundColor(Color.LightGray);
textView.Gravity = GravityFlags.CenterVertical;
textView.SetTextColor(Color.ParseColor("Blue"));
textView.TextSize = 16;
textView.SetPadding(20, 0, 20, 0);
countryAutoComplete.DropDownFooterView = textView;
=======
	List<String> countryList = new List<String>(); 
	countryList.Add ("Uganda");
	countryList.Add ("Ukraine");
	countryList.Add ("United Arab Emirates");
	countryList.Add ("United Kingdom");
	countryList.Add ("United States");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.ShowDropDownFooterView=true;


	TextView textView = new TextView(context);
            textView.Text = "Add New"
            textView.TextSize = 20;
			textView.setTextColor(Color.parseColor("Blue"));
            textView.SetPadding(20, 0, 20, 0);
			countryAutoComplete.DropDownFooterView=textView;
>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
	 
{% endhighlight %}

{% endtabs %}

<<<<<<< HEAD
=======
## Footer Height

The height of the Header in the SfAutoComplete can be adjusted by the property `DropDownFooterViewHeight`.

{% tabs %}

{% highlight C# %}

List<String> countryList = new List<String>(); 
    countryList.Add ("Uganda");
	countryList.Add ("Ukraine");
	countryList.Add ("United Arab Emirates");
	countryList.Add ("United Kingdom");
	countryList.Add ("United States");
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);

	//Set the Height of the Footer View 

    countryAutoComplete.DropDownFooterViewHeight= 50;

	TextView textView = new TextView(context);
    textView.Text = "Add New"
	textView.setTextColor(Color.parseColor("Blue"));
    textView.TextSize = 20;
    textView.SetPadding(20, 0, 20, 0);
	countryAutoComplete.DropDownFooterView=textView;


{% endhighlight %}

{% endtabs %}
>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
![](images/Footer.png)



 