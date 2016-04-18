---
layout: post
title: Precision Mode in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the precision mode of rating control
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Precision Mode

The precision mode defines the accuracy level of the rating control. It has Standard, Half and Exact options.

## Standard

The rating item will be filled completely based on the rating value.

{% highlight C# %}

	   sfRating.Precision=Precision.Standard;

{% endhighlight %}

![](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% highlight C# %}

	   sfRating.Precision=Precision.Half;

{% endhighlight %}

![](images/half.jpg) 

## Exact

The rating item will be filled exactly based on the rating value.

{% highlight C# %}

	   sfRating.Precision=Precision.Exact;

{% endhighlight %}

![](images/exact.jpg) 



