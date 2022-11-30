---
layout : post
title : Dealing with Suggestion Box in Xamarin.Android ComboBox Control | Syncfusion 
description : Learn here all about dealing with suggestion box in Syncfusion Essential Xamarin.Android ComboBox control, its elements, and more.
platform : Xamarin.Android 
control : ComboBox
documentation : ug
---

# Dealing with suggestion box in Xamarin.Android ComboBox
In the combobox control, the DropDown Box can placed in the following two positions:

* Bottom 

* Top 

Using the `SuggestionBoxPlacement` property, you can place the suggestion box at the top or bottom. 

## SuggestionBox placement at bottom

Displays the suggestion box at the bottom of the combo box control. 
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Bottom; 
 
{% endhighlight %}
{% endtabs %}

![Suggestion Box placement at bottom in Xamarin.Android ComboBox](images/bottom.png)

## SuggestionBox placement at top

Displays the suggestion box at the top of the combo box control. 
 
{% tabs %}
{% highlight c# %}

combobox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top; 
 
{% endhighlight %}
{% endtabs %}

![Suggestion Box placement at top in Xamarin.Android ComboBox](images/top.png)