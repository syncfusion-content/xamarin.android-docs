---
layout: post
title: FirstDayofWeek support in Syncfusion Calendar control for Xamarin.Android
description: Learn how to change the first day of week 
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# FirstDayofWeek

By default, the starting day will be Sunday. This can be modified using `FirstDayofWeek` property. Changing the first day of the week will be applied to both month and year view.

{% highlight c# %}
	
SfCalendar sfCalendar = new SfCalendar(this);

sfCalendar.FirstDayOfWeek= 4;

{% endhighlight %}

![](images/firstday_week.png)                                        



