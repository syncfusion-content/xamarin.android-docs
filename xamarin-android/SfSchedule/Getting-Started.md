---
layout: post
title: Getting started with Syncfusion Essential Schedule for Xamarin.Android
description: How to create a Schedule, add Appointments, enable Inline and other functionalities
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Getting started

This section explains you the steps required to render the `Meeting Room Booking Scheduler` using Schedule control by populating events(appointments) in the control. This section covers only the minimal features that you need to know to get started with the Schedule.

## Adding control reference to the application

Illustration for the procedures to install the Syncfusion Essential Studio can be referred from [Syncfusion Xamarin.Android components installation](http://help.syncfusion.com/Xamarin-Android/introduction/download-and-installation), `Syncfusion.SfSchedule.Android` should be used to add schedule reference in the application. 

## Initializing Schedule 

Create a SfSchedule instance in Main Activity and set schedule as a ContentView in onCreate() overridden method.

{% highlight c# %}  
    
    using Com.Syncfusion.Schedule;

    protected override void OnCreate(Bundle bundle)
    {
        base.OnCreate(bundle);
        SfSchedule meetingRoomScheduler = new SfSchedule(this);
        // Set our view from the "main" layout resource
        SetContentView(sfschedule);
    }
    
{% endhighlight %}

![](GettingStarted_images/GettingStarted_img1.jpeg)

You can change the default UI of schedule using `ScheduleView` to display the dates in different layouts available in the control.

{% highlight c# %}

    SfSchedule meetingRoomScheduler = new SfSchedule(this);
    meetingRoomScheduler.ScheduleView = ScheduleView.WeekView;
    // Set our view from the "main" layout resource
    SetContentView(meetingRoomScheduler);
    
{% endhighlight %}

![](GettingStarted_images/GettingStarted_img2.jpeg)

## Populating Events

You can also add events to the schedule by creating collection of `ScheduleAppointment` using `ScheduleAppointmentCollection`. 

{% highlight c# %}

    ScheduleAppointmentCollection appointmentCollection;
    //..//
    //creating new instance for schedule
    SfSchedule meetingRoomScheduler = new SfSchedule(this);
    meetingRoomScheduler.ScheduleView = ScheduleView.WeekView;
    meetingRoomScheduler.Appointments = ListOfMeeting;
    
    private void BookingAppointments()
    {
    ListOfMeeting = new ScheduleAppointmentCollection();
    Java.Util.Random randomTime = new Java.Util.Random();
    List<int> randomTimeCollection = GettingTimeRanges();
    InitializeDataForBookings();
    Calendar calendar = Calendar.Instance;

    Calendar DateFrom = Calendar.Instance;
    DateFrom.Add(CalendarField.Date, -10);

    Calendar DateTo = Calendar.Instance;
    DateTo.Add(CalendarField.Date, 10);

    Calendar dateRangeStart = Calendar.Instance;
    dateRangeStart.Add(CalendarField.Date, -3);

    Calendar dateRangeEnd = Calendar.Instance;
    dateRangeEnd.Add(CalendarField.Date, 3);

    for (calendar = DateFrom; calendar.Before(DateTo);
    calendar.Add(CalendarField.Date, 1))
    {
    if (calendar.After(dateRangeStart) && calendar.Before(dateRangeEnd))
    {
    for (int AdditionalAppointmentIndex = 0; AdditionalAppointmentIndex < 3; AdditionalAppointmentIndex++)
    {
    ScheduleAppointment meeting = new ScheduleAppointment();
    int hour = randomTime.NextInt(((15 -13) + 1) + 9);
    Calendar startTimeCalendar = Calendar.Instance;
    startTimeCalendar.Set(calendar.Get(CalendarField.Year),calendar.Get(CalendarField.Month), calendar.Get(CalendarField.Date), hour, 0);
    meeting.StartTime = startTimeCalendar;
    Calendar endTimeCalendar = Calendar.Instance;
    endTimeCalendar.Set(calendar.Get(CalendarField.Year), calendar.Get(CalendarField.Month), calendar.Get(CalendarField.Date), hour + 1, 0);
    meeting.EndTime = endTimeCalendar;
    meeting.Color = Color.ParseColor(colorCollection[randomTime.NextInt(9)]);
    meeting.Subject = currentDayMeetings[randomTime.NextInt(9)];
    ListOfMeeting.Add(meeting);
    }
    }

    else
    {
    ScheduleAppointment meeting = new ScheduleAppointment();
    int hour =randomTime.NextInt(((15 - 10) + 1) + 9);
    Calendar startTimeCalendar = Calendar.Instance;
    startTimeCalendar.Set(calendar.Get(CalendarField.Year),calendar.Get(CalendarField.Month),calendar.Get(CalendarField.Date), hour, 0);
    meeting.StartTime = startTimeCalendar;
    Calendar endTimeCalendar = Calendar.Instance;
    endTimeCalendar.Set(calendar.Get(CalendarField.Year),calendar.Get(CalendarField.Month), calendar.Get(CalendarField.Date), hour+1, 0);
    meeting.EndTime = endTimeCalendar;
    meeting.Color = Color.ParseColor(colorCollection[randomTime.NextInt(9)]);
    meeting.Subject = currentDayMeetings[randomTime.NextInt(9)];
    ListOfMeeting.Add(meeting);	
    }
    }
    }

{% endhighlight %}

You can add `Subject` and `Color` to the appointments created by creating a collection for the same.

{% highlight c# %}

    List<string> meetingCollection;
    List<string> colorCollection;
    
    private void InitializeDataForBookings()
    {
    meetingCollection = new List<string>();
    meetingCollection.Add("GoToMeeting");
    meetingCollection.Add("Business Meeting");
    meetingCollection.Add("Conference");
    meetingCollection.Add("Project Status Discussion");
    meetingCollection.Add("Auditing");
    meetingCollection.Add("Client Meeting");
    meetingCollection.Add("Generate Report");
    meetingCollection.Add("Target Meeting");
    meetingCollection.Add("General Meeting");
    meetingCollection.Add("Pay House Rent");
    meetingCollection.Add("Car Service");
    meetingCollection.Add("Medical Check Up");
    meetingCollection.Add("Wedding Anniversary");
    meetingCollection.Add("Sam's Birthday");
    meetingCollection.Add("Jenny's Birthday");

    colorCollection = new List<string>();
    colorCollection.Add("#117EB4");
    colorCollection.Add("#B4112E");
    colorCollection.Add("#C44343");
    colorCollection.Add("#11B45E");
    colorCollection.Add("#43BEC4");
    colorCollection.Add("#B4112E");
    colorCollection.Add("#C44343");
    colorCollection.Add("#117EB4");
    colorCollection.Add("#C4435A");
    colorCollection.Add("#DF5348");
    colorCollection.Add("#43c484");
    colorCollection.Add("#11B49B");
    colorCollection.Add("#C44378");
    colorCollection.Add("#DF8D48");
    colorCollection.Add("#11B45E");
    colorCollection.Add("#43BEC4");
    }
	
{% endhighlight %}

![](GettingStarted_images/GettingStarted_img3.jpeg)
