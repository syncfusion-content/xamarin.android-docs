---
layout : post
title : No Results Found Text in Syncfusion® SfAutoComplete Control for Xamarin.Android
description : Learn how to display and customize the no results found text in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# No Results Found

When the entered item is not in the suggestion list, SfAutoComplete displays text indicating that no search results were found. You can set the desired text to be displayed when no results are found using the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.NoResultsFoundText="No Results Found";
	 
{% endhighlight %}

{% endtabs %}

![No results found example](images/NoResultsFound.png)

## Customizing No Results Found Text

The `NoResultsFoundTextColor`, `NoResultsFoundFontSize`, and `NoResultsFoundTypeface` properties are used to customize the foreground color, font size, and typeface of the no results found text.

{% tabs %}

{% highlight c# %}

countryAutoComplete.NoResultsFoundText = "No Results Found";
countryAutoComplete.NoResultsFoundFontSize = 20;
countryAutoComplete.NoResultsFoundTextColor = Android.Graphics.Color.DarkGreen;
countryAutoComplete.NoResultsFoundTypeface = Typeface.CreateFromAsset(this.Assets, "Pacifico.ttf");

{% endhighlight %}

{% endtabs %}

![No results found customization example](images/NoResultsFound_Customization.jpg)
