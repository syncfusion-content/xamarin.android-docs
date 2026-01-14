---
layout: post
title: Restrict User Selection in Syncfusion® Rating for Xamarin.Android
description: Learn how to restrict user interaction and make the Rating control read-only using the ReadOnly property.
platform: xamarin.android
control: Rating
documentation: ug
---

# Restrict User Selection

The SfRating control provides the ability to control user interaction through the `ReadOnly` property. When enabled, this property prevents users from modifying the rating value, making the control display-only while maintaining its visual appearance. 

N> By default, property value is set to False.

{% tabs %}

{% highlight C# %}

	   rating.ReadOnly= true;

{% endhighlight %}

{% endtabs %}

![Read-Only Rating Control](images/readOnly.jpg)

