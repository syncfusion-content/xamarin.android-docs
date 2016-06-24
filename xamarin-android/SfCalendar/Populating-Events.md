---
layout: post
title: Populating Events in Syncfusion Calendar control for Xamarin.Android
description: Learn how to populate events inside a cell and inline events descriptions
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Populating Events

Calendar control has an inbuilt capability to display the events based on the calendar events collection provided to `DataSource` property. For events to be listed for a particular day, enable the inline feature in month view cell.

The default UI of the inline view with events will be like list of events with a Gray background

![](images/inline_events.png)                                        


Default UI of the inline view without events will be hinting No Events available on a particular day.

![](images/no_events.png)                                        


Inline event support can be toggled on / off with `ShowEventsInline` property.

{% highlight c# %}

	sfcalendar.showInLineEvent=True;

{% endhighlight %}

N> The Inline function will be available only in MonthView with Single selection mode.

## Adding events using Collection

Calendar Events collection can be provided to calendar using the following steps. `CalendarEventCollection` is a class, which holds the details about the events to be rendered in calendar. 

`CalendarInlineEvent` has some basic properties such as `StartTime`, `EndTime` and `Subject`.

{% highlight C# %}
		   
		   CalendarEventCollection eventsCollection =new CalendarEventCollection();
		   CalendarInlineEvent events=new CalendarInlineEvent();
           DateTime d=new DateTime(2015,1,1);
           DateTime d1=new DateTime(2015,1,1);
           events.StartTime=d;
           events.EndTime=d1;
           events.Subject=”Go to Meeting”;
           events.Color=Color.RED;
		   
{% endhighlight %}

Create the collection of the calendar events by setting required details using above mentioned properties for each events.

{% highlight c# %}

	eventsCollection.Add(events);
	
{% endhighlight %}

Assign the created collection to the `DataSource` property of Calendar 

{% highlight c# %}

	calendar.DataSource(eventsCollection); 

{% endhighlight %}

![](images/inline_events.png)                                        



