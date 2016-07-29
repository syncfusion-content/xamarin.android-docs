---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Android
description: A quick tour to initial users on Syncfusion calendar control Xamarin.Android platform 
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Getting Started

This section explains you the steps required to render the SfCalendar control, to change selection mode, set min max dates and black out dates for the control. This section covers only the minimal features that you need to know to get started with the SfCalendar.

![](images/gettingstarted.png)

## Creating your first SfCalendar in Xamarin.Android.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfCalendar.Andriod.dll

### Add and Configure the SfCalendar

The following steps explain on how to create an SfCalendar and configure its elements,

* Adding reference to Calendar.

{% highlight c# %}

	using Com.Syncfusion.Calendar; 

{% endhighlight %}

* Create an instance of SfCalendar.

{% highlight c# %}
	
	SfCalendar calendar = new SfCalendar(this);
	setContentView(calendar);
	
{% endhighlight %}

### Enabling Multiple Selection 

To enable multiple selection, Change the selection type using `SelectionMode` property. Check the [Selection Mode](http://help.syncfusion.com/android/sfcalendar/selectionmode)  section for more details.

{% highlight c# %}

	SfCalendar calendar = new SfCalendar (this);
	calendar.SelectionMode=SelectionMode.MultiSelection;

{% endhighlight %}

### Setting blackout dates

Add the dates into `BlackOutDates` property, that needs to be disabled among visible dates. Check the [BlackOutDates](http://help.syncfusion.com/android/sfcalendar/blackoutdates) section for more details.

For instance add all the holiday dates to blackout dates property.

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar (this);
	List<DateTime> black_dates = new List<DateTime>();
	for (int i = 0; i < 5; i++)
	{
		DateTime date = DateTime.Now.Date.AddDays(i+7);
		black_dates.Add(date);
    }
	calendar.BlackoutDates = black_dates;


{% endhighlight %}

### Restricting Dates

Set `MinDate` and `MaxDate` property to limit visible dates range. Check the [Min Max dates](http://help.syncfusion.com/android/sfcalendar/datenavigation-and-gesture#min-max-dates) section for more details.

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar (this);
	calendar.MinDate = new DateTime(2014,4,1);
	calendar.MaxDate = new DateTime(2018,4,1);


{% endhighlight %}
