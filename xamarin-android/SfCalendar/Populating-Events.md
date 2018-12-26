---
layout: post
title: Populating Events in Syncfusion Calendar control for Xamarin.Android
description: Learn how to populate events inside a cell and inline events descriptions
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Populating Events

SfCalendar control has an built-in capability to display the events based on the calendar events collection provided to `DataSource` property. For events to be listed for a particular day, enable the inline feature in month view cell.

The default UI of the inline view with events will be like list of events with a Gray background

![](images/inline_events.png)                                        


Default UI of the inline view without events will be hinting No Events available on a particular day.

![](images/no_events.png)                                        


Inline event support can be toggled on / off with `ShowEventsInline` property.

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);

sfcalendar.ShowEventsInline=True;

{% endhighlight %}

N> The Inline function will be available only in MonthView with Single selection mode.

## Adding events using Collection

Calendar Events collection can be provided to SfCalendar using the following steps. `CalendarEventCollection` is a class, which holds the details about the events to be rendered in SfCalendar. 

`CalendarInlineEvent` has some basic properties such as `StartTime`, `EndTime`, `Subject` and `Color`

{% highlight C# %}
		   
SfCalendar sfCalendar = new SfCalendar(this);

CalendarEventCollection eventsCollection = new CalendarEventCollection();
CalendarInlineEvent events = new CalendarInlineEvent();

//starting date of event
Calendar startEventDate = Calendar.Instance;
startEventDate.Set(2015, 9, 26, 10, 0, 0);
events.StartTime = startEventDate;

//ending date of event
Calendar endEventDate = Calendar.Instance;
endEventDate.Set(2015, 9, 26, 12, 0, 0);
events.EndTime = endEventDate;

//subject which will be going to add as content in Inline event appointments
events.Subject = "Business Meeting";

//Indicator color in appointments
events.Color = Android.Graphics.Color.Red;

eventsCollection.Add(events);

//Add collection of events as source of SfCalendar

sfCalendar.DataSource = eventsCollection;

SetContentView(sfCalendar);
		   
{% endhighlight %}

Create the collection of the calendar events by setting required details using above mentioned properties for each events.

{% highlight c# %}

	eventsCollection.Add(events);
	
{% endhighlight %}

Assign the created collection to the `DataSource` property of SfCalendar 

{% highlight c# %}

	calendar.DataSource(eventsCollection); 

{% endhighlight %}

![](images/inline_events.png)      


## Inline / Agenda View Appearance

You can customize the inline item view by [OnInlineItemLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfCalendar.Android~Com.Syncfusion.Calendar.SfCalendar~InlineItemLoaded_EV.html) Event using in SfCalendar, using View of [InlineItemLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfCalendar.Android~Com.Syncfusion.Calendar.InlineItemLoadedEventArgs.html) argument. You can get the details of Appointment in the Appointment argument.

{% highlight c# %}

	calendar.InlineItemLoaded += Calendar_InlineItemLoaded; 

	.....

	void Calendar_InlineItemLoaded(object sender, InlineItemLoadedEventArgs e)
	{
		var appointment = e.CalendarInlineEvent;
		Button button = new Button(this);
		button.Text = "Appointment :" + appointment.Subject;
		button.SetBackgroundColor(Color.Blue);
		button.SetTextColor(Color.White);
		e.View = button;
	} 

{% endhighlight %}
                                  



