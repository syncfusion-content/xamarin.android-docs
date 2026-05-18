---
layout: post
title: Filtering Options in Syncfusion® SfComboBox for Xamarin.Android
description: Learn how to enable and configure text filtering in the SfComboBox dropdown list for enhanced user experience
platform: xamarin.android
control: SfComboBox
documentation: ug
---

# Filtering Options

The SfComboBox control provides filtering functionality that allows users to filter the dropdown list based on the text they type. You can enable this feature by setting the `AllowFiltering` boolean property to `true`.

N> The AllowFiltering property works only when the IsEditableMode property is set to true.

{% tabs %}

{% highlight C# %}

combobox = new SfComboBox(); 
combobox.IsEditableMode = true; 
combobox.AllowFiltering = true; 

{% endhighlight %}

{% endtabs %}

![SfComboBox filtering demonstration](images/filtering.png)
