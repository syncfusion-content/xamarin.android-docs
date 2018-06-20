---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.Android
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin.android
control: SfSchedule
documentation: ug

---


# Appointments

[ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment.html) is a class, which holds the details about the appointment to be rendered in schedule. It has some basic properties such as [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~StartTime.html), [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~EndTime.html), [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~Subject.html) and some additional information about the appointment can be added using [Color](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~Color.html), [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~Notes.html), [Location](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~Location.html), [All Day](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~IsAllDay.html), [Recurring properties](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~RecurrenceProperties.html).

{% tabs %}
{% highlight c# %}
using Com.Syncfusion.Schedule;
using Java.Util;

//Creating an instance for SfSchedule Control
SfSchedule schedule = new SfSchedule(this);

// Creating an instance for schedule appointment Collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new   ScheduleAppointmentCollection();

Calendar currentDate = Calendar.Instance;
Calendar startTime = (Calendar)currentDate.Clone();

//setting start time for the event
startTime.Set(currentDate.Get(CalendarField.Year),
              currentDate.Get(CalendarField.Month),
              currentDate.Get(CalendarField.DayOfMonth),
              10, 0, 0);

Calendar endTime = (Calendar)currentDate.Clone();

//setting end time for the event
endTime.Set(currentDate.Get(CalendarField.Year),
            currentDate.Get(CalendarField.Month),
            currentDate.Get(CalendarField.DayOfMonth),
            12, 0, 0);

//Adding Schedule appointment in schedule appointment collection
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = startTime,
    EndTime = endTime,
    Subject = "Client Meeting",
    Color = Color.Red,
    Location = "Hutchison road",
});

//Adding schedule appointment collection to SfSchedule appointments
schedule.Appointments = scheduleAppointmentCollection;
SetContentView(schedule);
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointment.png)

## Minimum Appointment Height

[MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~MinHeight.html) of an appointment is to set an arbitrary height to appointments when it has minimum duration, so that the subject can be readable.

{% tabs %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule(this);
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
Calendar currentDate = Calendar.Instance;
Calendar startTime = (Calendar)currentDate.Clone();
Calendar endTime = (Calendar)currentDate.Clone();

startTime.Set(currentDate.Get(CalendarField.Year),
              currentDate.Get(CalendarField.Month),
              currentDate.Get(CalendarField.DayOfMonth),
              9,0,0);
endTime.Set(currentDate.Get(CalendarField.Year),
            currentDate.Get(CalendarField.Month),
            currentDate.Get(CalendarField.DayOfMonth),
            9,0,0);
Calendar startTime1 = (Calendar)currentDate.Clone();
Calendar endTime1 = (Calendar)currentDate.Clone();
startTime1.Set(currentDate.Get(CalendarField.Year),
               currentDate.Get(CalendarField.Month),
               currentDate.Get(CalendarField.DayOfMonth),
               11,0,0);
endTime1.Set(currentDate.Get(CalendarField.Year),
             currentDate.Get(CalendarField.Month),
             currentDate.Get(CalendarField.DayOfMonth),
             12,0,0);
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = startTime,
    EndTime = endTime,
    Subject = "Client Meeting",
    MinHeight = 30,
    Color = Color.ParseColor("#FFD80073")
});
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = startTime1,
    EndTime = endTime1,
    Subject = "Anniversary",
    Color = Color.ParseColor("#FFA2C139")
});
schedule.Appointments= scheduleAppointmentCollection;
SetContentView(schedule);
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/minheight.png)

>**NOTE**
* `MinHeight` value will be set, when the an appointment height (duration) value lesser than MinHeight. 
* Appointment height (duration) value will be set, when the appointment height (duration) value greater than `MinHeight`.
* TimeInterval value will be set, when Minimum Height greater than TimeInterval with lesser appointment height (duration). 
* `MinHeight` has ScheduleAppointmentMapping Support. 
* All day Appointment does not support `MinHeight`.

## Mapping
Schedule supports full data binding to any type of IEnumerable source. Specify the [AppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping.html) attributes to map the properties in the underlying data source to the schedule appointments.

| PropertyName | Description |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~StartTime.html) | This property is to map the property name of custom class which is equivalent for StartTime of ScheduleAppointment. |
| [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~EndTime.html)| This property is to map the property name of custom class which is equivalent for EndTime of ScheduleAppointment. |
| [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~Subject.html) | This property is to map the property name of custom class which is equivalent for Subject of ScheduleAppointment. |
| [Color](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~Color.html) | This property is to map the property name of custom class which is equivalent for Color of ScheduleAppointment. |
| [IsAllDay](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~IsAllDay.html) | This property is to map the property name of custom class which is equivalent for IsAllDay of ScheduleAppointment. |
| [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~RecurrenceRule.html) | This property is to map the property name of custom class which is equivalent for RecurrenceRule of ScheduleAppointment. |
| [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~Notes.html) | This property is to map the property name of custom class which is equivalent for Notes of ScheduleAppointment. |
| [Location](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~Location.html) | This  property is to map the property name of custom class which is  equivalent for Location of ScheduleAppointment. |
| [MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~MinHeight.html) | This property is to map the property name of custom class which is equivalent for MinHeight of ScheduleAppointment. |
| [StartTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~StartTimeZone.html) | This property is to map the property name of custom class which is equivalent for StartTimeZone of ScheduleAppointment. |
| [EndTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.AppointmentMapping~EndTimeZone.html) | This property is to map the property name of custom class which is equivalent for EndTimeZone of ScheduleAppointment. |
 
>**Note**
CustomAppointment class should contain two Calendar fields and a string field as mandatory.

### Creating custom Appointments
You can create custom class `Meeting` with mandatory fields `From`, `To` and `EventName`.

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents custom data properties.   
/// </summary> 
public class Meeting
{
	public string EventName { get; set; }
	public Calendar	 From { get; set; }
	public Calendar To { get; set; }
	public int Color { get; set; }
}
{% endhighlight %}
{% endtabs %}

>**Note**
You can inherit this class from INotifyPropertyChanged for dynamic changes in custom data.

You can map those properties of `Meeting` class with our SfSchedule control by using [AppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin-Android/Syncfusion.SfSchedule.Android~Syncfusion.SfSchedule.Android.SfSchedule~AppointmentMapping.html).

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents custom data properties.   
/// </summary> 
 AppointmentMapping dataMapping = new AppointmentMapping();
 dataMapping.Subject = "EventName";
 dataMapping.StartTime = "From";
 dataMapping.EndTime = "To";
 dataMapping.Color = "Color";
 sschedule.AppointmentMapping = dataMapping;
{% endhighlight %}
{% endtabs %}


You can schedule meetings for a day by setting `From` and `To` of `Meeting` class. Create meetings of type `ObservableCollection <Meeting>` and assign those appointments collection `Meetings` to the `ItemsSource` property which is of `IEnumerable` type.

{% tabs %}
{% highlight c# %}
Calendar currentDate = Calendar.Instance;
Calendar startTime = (Calendar)currentDate.Clone();
Calendar endTime = (Calendar)currentDate.Clone();
//setting start time for the event
startTime.Set(currentDate.Get(CalendarField.Year),
			  currentDate.Get(CalendarField.Month),
			  currentDate.Get(CalendarField.DayOfMonth),
			  10, 0, 0);
//setting end time for the event
endTime.Set(currentDate.Get(CalendarField.Year),
			currentDate.Get(CalendarField.Month),
			currentDate.Get(CalendarField.DayOfMonth),
			11, 0, 0);

// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = startTime;
// Setting end time of an event
meeting.To = endTime;
// Setting start time for an event
meeting.EventName = "Anniversary";
// Setting color for an event
meeting.Color = Color.Green;
// Creating instance for collection of custom appointments
var Meetings = new ObservableCollection<Meeting>();
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);
// Adding custom appointments in DataSource of SfSchedule
schedule.ItemsSource = Meetings;
{% endhighlight %}
{% endtabs %}


## Spanned Appointments
Spanned Appointment is an appointment which lasts more than 24 hours. It doesn’t block out time slots in `SfSchedule`, it will render in [All-Day appointment](https://help.syncfusion.com/xamarin-android/sfschedule/data-bindings#all-day-appointment-panel) panel exclusively.

{% tabs %}
{% highlight c# %}
using Com.Syncfusion.Schedule;
using Java.Util;

//Creating an instance for SfSchedule Control
SfSchedule schedule = new SfSchedule(this);

// Creating an instance for schedule appointment Collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new   ScheduleAppointmentCollection();

Calendar currentDate = Calendar.Instance;
Calendar startTime = (Calendar)currentDate.Clone();

//setting start time for the event
startTime.Set(currentDate.Get(CalendarField.Year),
              currentDate.Get(CalendarField.Month),
              currentDate.Get(CalendarField.DayOfMonth),
              10, 0, 0);

Calendar endTime = (Calendar)currentDate.Clone();

//setting end time for the event
endTime.Set(currentDate.Get(CalendarField.Year),
            currentDate.Get(CalendarField.Month),
            currentDate.Get(CalendarField.DayOfMonth)+2,
            12, 0, 0);

//Adding Schedule appointment in schedule appointment collection
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = startTime,
    EndTime = endTime,
    Subject = "Client Meeting",
    Color = Color.Red,
    Location = "Hutchison road",
});

//Adding schedule appointment collection to SfSchedule appointments
schedule.Appointments = scheduleAppointmentCollection;
SetContentView(schedule);
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/span.png)

## All Day Appointments
All-Day appointment is an appointment which is scheduled for a whole day. It can be set by using `IsAllDay` property in the `ScheduleAppointment`.

{% tabs %}
{% highlight c# %}
//Adding Schedule appointment in schedule appointment collection
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = startTime,
    EndTime = endTime,
    Subject = "Client Meeting",
    Color = Color.Red,
    Location = "Hutchison road",
    IsAllDay = true
});
{% endhighlight %}
{% endtabs %}

>**NOTE**
Appointment which lasts through an entire day (exact 24 hours) will be considered as all day appointment without setting `IsAllDay` property. For example  06/09/2018 12:00AM to 06/10/2018 12:00AM.

### All-Day Appointment Panel
All-day appointment and Spanned appointment doesn't block out entire time slot in SfSchedule, rather it will render in separate layout exclusively for all-day appointment. It can be enabled by setting `ShowAllDay` property of `DayViewSettings`, `WeekViewSettings` and `WorkWeekViewSettings` of `DayView`, `WeekView` and `WorkWeekView` respectively.

{% tabs %}
{% highlight c# %}
//Setting schedule view
schedule.ScheduleView = ScheduleView.WeekView;

//Creating week view settings for SfSchedule WeekView
WeekViewSettings weekViewSettings = new WeekViewSettings();
weekViewSettings.ShowAllDay = true;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

>**NOTE**
Appointments which lasts less than 24 hours with different start date and end date will be rendered in time slot.

All-Day panel background can be customized by setting `AllDayAppointmentBackgroundColor` 
of the respective view settings.

{% tabs %}
{% highlight c# %}
weekViewSettings.AllDayAppointmentBackgroundColor = Color.Silver;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/allday.png)

## Recurrence Appointment
Recurring appointment on a daily, weekly, monthly, or yearly interval. Recurring appointments can be created by setting `RecurrenceRule` property in Schedule appointments.

### Recurrence Rule
The `RecurrenceRule` is a string value, that contains the details of the recurrence appointments like repeat type - daily/weekly/monthly/yearly, how many times it needs to be repeated, the interval duration and also the time period to render the appointment, etc.
`RecurrenceRule` has the following properties and based on this property value, the recurrence appointments are rendered in the SfSchedule control with its respective time period.

| PropertyName | Purpose |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| FREQ | Maintains the Repeat type value of the appointment. (Example: Daily, Weekly, Monthly, Yearly, Every week day) Example: FREQ=DAILY;INTERVAL=1 |
| INTERVAL | Maintains the interval value of the appointments. For example, when you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday. (creates the appointment on all days by leaving the interval of one day gap) Example: FREQ=DAILY;INTERVAL=1 |
| COUNT | It holds the appointment’s count value. For example, when the recurrence appointment count value is 10, it means 10 appointments are created in the recurrence series. Example: FREQ=DAILY;INTERVAL=1;COUNT=10 |
| UNTIL | This property is used to store the recurrence end date value. For example, when you set the end date of appointment as 6/30/2014, the UNTIL property holds the end date value when the recurrence actually ends. Example: FREQ=DAILY;INTERVAL=1;UNTIL=8/25/2014 |
| BYDAY | It holds the “DAY” values of an appointment to render.For example, when you create the weekly appointment, select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday).  When Monday is selected, the first two letters of the selected day “MO” is stored in the “BYDAY” property.  When you select multiple days, the values are separated by commas. Example: FREQ=WEEKLY;INTERVAL=1;BYDAY=MO,WE;COUNT=10 |
| BYMONTHDAY | This property is used to store the date value of the Month while creating the Month recurrence appointment. For example, when you create a Monthly recurrence appointment in the date 3, it means the BYMONTHDAY holds the value 3 and creates the appointment on 3rd day of every month. Example: FREQ=MONTHLY;BYMONTHDAY=3;INTERVAL=1;COUNT=10 |
| BYMONTH | This property is used to store the index value of the selected Month while creating the yearly appointments. For example, when you create the yearly appointment in the Month June, it means the index value for June month is 6 and it is stored in the BYMONTH field.  The appointment is created on every 6th month of a year. Example: FREQ=YEARLY;BYMONTHDAY=16;BYMONTH=6;INTERVAL=1;COUNT=10 |
| BYSETPOS | This property is used to store the index value of the week. For example, when you create the monthly appointment in second week of the month, the index value of the second week (2) is stored in BYSETPOS. Example: FREQ=MONTHLY;BYDAY=MO;BYSETPOS=2;UNTIL=8/11/2014 |

### Recurrence Pattern
Recurrence pattern used in the control are in iCal standard. Schedule control supports all four types of [recurrence patterns](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties.html).

| RecurrenceType | RecurrenceProperties | Description                                                                                 |
|----------------|----------------------|---------------------------------------------------------------------------------------------|
| Daily | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Interval.html)    | Gets or sets the day interval on which recurrence has to be set.|
|  | [IsDailyEveryNDays](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~IsDailyEveryNDays.html) | Checks whether the event occurs Daily Every N days.                                         |
| Weekly  | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Interval.html)  | Gets or sets the day interval on which recurrence has to be set.|
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~DayOfWeek.html) | Gets or sets the day of week on which recurrence has to be set.|
|                | [WeekDays](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~WeekDays.html)  | Gets or sets the day/days in a week on which recurrence has to be set.|
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Week.html) | Gets or sets the week of month on which recurrence has to be set.|
| Monthly        | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Interval.html) | Gets or sets the day interval on which  recurrence has to be set.|
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~DayOfWeek.html)  | Gets or sets the day of week on which  recurrence has to be set.|
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Week.html) | Gets or sets the week of month on which recurrence has to be set.|
|                | [DayOfMonth](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~DayOfMonth.html) | Gets or sets the day on which recurrence has to be set for every month.|
|				 | [IsMonthlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~IsMonthlySpecific.html) | Checks whether the event is Monthly specific event.|
| Yearly         | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Interval.html) | Gets or sets the day interval on which recurrence has to be set.|
|                | [DayOfMonth](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~DayOfMonth.html) | Gets or sets the day on which recurrence has to be set for every month.|
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~DayOfWeek.html) | Gets or sets the day of week on which  recurrence has to be set.|
|				 | [Month](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Month.html)				| Gets or sets the specific month of year on which recurrence has to be set.|
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~Week.html) | Gets or sets the week of month on which recurrence has to be set.|
|				 | [IsYearlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~IsYearlySpecific.html) | Checks whether the event is Yearly Specific.|
| Common         | [RecurrenceRange](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~RecurrenceRange.html) | Gets or sets the type of the recurrence range for the time limit of recurrence appointment. |
|                | [RecurrenceCount](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~RecurrenceCount.html) | Gets or sets the count for recurring appointment.|
|                | [StartDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~StartDate.html) | Gets or sets the date to start the recurrence appointment.|
|                | [EndDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~EndDate.html) | Gets or sets the date to end the recurrence appointment.|
| 				 | [IsSpecific](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.RecurrenceProperties~IsSpecific.html) | Checks whether the event occurs in specific recurrence type.|

Find the following `RecurrenceRule` possibilities available in the Schedule control while creating the recurrence appointment.

| PossibilityType | Description | RecurrenceProperties | Examples |
|-----------------|----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Daily | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=DAILY; INTERVAL=1 |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 15 | FREQ=DAILY; INTERVAL=1; COUNT=5 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 06, 20) | FREQ=DAILY; INTERVAL=1; UNTIL=06/20/2017 |
|  | Appointment is created with Every (Interval) | RecurrenceType = RecurrenceType.Daily, Interval = 2, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=DAILY; INTERVAL=2; COUNT=10 |
| Weekly | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday `|`WeekDays.Wednesday`|`WeekDays.Friday,RecurrenceRange  = RecurrenceRange.NoEndDate | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO, WE, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Thursday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=1; BYDAY=TH; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 07, 20) | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO; UNTIL=07/20/2017 |
|  | Appointment is created with selecting multiple day | RecurrenceType = RecurrenceType.Weekly, Interval = 2, WeekDays = WeekDays.Monday`|`WeekDays.Wednesday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=2; BYDAY=MO, WE, FR; COUNT=10 |
| Every Day | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 07, 15) | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; UNTIL=07/15/2017 |
| Monthly | Appointment is created with selected date Ends Never | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 15, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=MONTHLY; BYMONTHDAY=15; INTERVAL=1 |
|  | Appointment is created with selected date and Ends After | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 16, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=MONTHLY; BYMONTHDAY=16; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and Ends On | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 16, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYMONTHDAY=17; INTERVAL=1; UNTIL=06/11/2018 |
|  | Appointment is created with selected day Ends Never | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 2, DayOfWeek = 6, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=2; INTERVAL=1 |
|  | Appointment is created with selected day and Ends After | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 4, DayOfWeek = 4, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=MONTHLY; BYDAY=WE; BYSETPOS=4; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected day and Ends On | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 4, DayOfWeek = 6, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=4; INTERVAL=1; UNTIL=06/11/2018 |
| Yearly | Appointment is created with selected date and month Ends Never | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 15, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=YEARLY; BYMONTHDAY=15; BYMONTH=12; INTERVAL=1 |
|  | Appointment is created with selected date and month Ends After | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 10, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=YEARLY; BYMONTHDAY=10; BYMONTH=12; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and month Ends On | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 12, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=YEARLY; BYMONTHDAY=12; BYMONTH=12; INTERVAL=1; UNTIL=06/11//2018 |

N> `SfSchedule` does not support Editing and Deleting of Recurring appointment's occurrences.


### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recurring appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

{% tabs %}
{% highlight c# %}
// Creating instance for schedule appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();


//Adding schedule appointment in schedule appointment collection
var scheduleAppointment = new ScheduleAppointment()
{
    StartTime = startTime,
    EndTime = endTime,
    Subject = "Client Meeting",
    Location = "Hutchison road",
};


//Adding schedule appointment in schedule appointment collection
scheduleAppointmentCollection.Add(scheduleAppointment);

// Creating recurrence rule
RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
recurrenceProperties.RecurrenceType = RecurrenceType.Daily;
recurrenceProperties.RecurrenceRange = RecurrenceRange.Count;
recurrenceProperties.Interval = 2;
recurrenceProperties.IsDailyEveryNDays = true;
recurrenceProperties.RecurrenceCount = 10;

// Setting recurrence rule to schedule appointment
scheduleAppointment.RecurrenceRule = ScheduleHelper.RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

//Adding Schedule appointment collection to SfSchedule appointments
schedule.Appointments = scheduleAppointmentCollection;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/recurrence.png)

## Drag and Drop Appointments
Appointments can be rescheduled using the drag and drop operation. To perform drag-and-drop operations within the schedule, enable the [AllowAppointmentDrag](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AllowAppointmentDrag.html) property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
schedule.AllowAppointmentDrag = true;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/draganddrop.gif)

### Handle dragging based on the appointment
Using [AppointmentDragStarting](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragStarting_EV.html) event, you can get the appointment details and handle whether the appointment can be draggable or not. This event will be triggered when the appointment is started dragging. The [AppointmentDragStartingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragStartingEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragStartingEventArgs~Appointment.html) - Gets the dragged appointment details.
[Cancel](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragStartingEventArgs~Cancel.html) - Appointment dragging can be handled (enable/disable) using this boolean property.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

...

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
{
var appointment = e.Appointment;
e.Cancel = false;
}
{% endhighlight %}
{% endtabs %}

#### Disabling dragging when the appointment is AllDay appointment
Using `Cancel` property in the `AppointmentDragStartingEventArgs` argument of Schedule `AppointmentDragStarting` event, you can enable/disable the appointment dragging based on the requirement. In the below, we have disabled the appointment dragging when the appointment is AllDay appointment.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

...

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
{
var appointment = e.Appointment as ScheduleAppointment;

if (appointment.IsAllDay)
{
e.Cancel = true;
}
}
{% endhighlight %}
{% endtabs %}

### Get the dragging appointment position
Using [AppointmentDragOver](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragOver_EV.html) event, you can get the dragging appointment details, position and time of the particular location. The event will be continuously triggered when the appointment is being dragged. The [AppointmentDragEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragEventArgs~Appointment.html) - Gets the dragging appointment details.
[DraggingPoint](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragEventArgs~DraggingPoint.html) - Gets the dragging point (X, Y) of the appointment in Schedule.
[DraggingTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDragEventArgs~DraggingTime.html) - Gets the dragging time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

...

private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
{
var appointment = e.Appointment;
var draggingPoint = e.DraggingPoint;
var draggingTime = e.DraggingTime;
}
{% endhighlight %}
{% endtabs %}

#### Displaying alert while dragging appointment over the blocked time slots
Using `draggingPoint` and `draggingTime` properties in the `AppointmentDragEventArgs` of Schedule `AppointmentDragOver` event you can get the current position and time of dragging appointment. In the below, we have indicated the message while dragging over the Schedule `NonAccessibleBlock`.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

...

private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
{
//// Comparing the NonAccessibleBlock Start hour with the dragging time
NSCalendar calendar = NSCalendar.CurrentCalendar;
NSDateComponents draggingTime = calendar.Components(NSCalendarUnit.Year |
NSCalendarUnit.Month |
NSCalendarUnit.Day |
NSCalendarUnit.Hour |
NSCalendarUnit.Minute |
NSCalendarUnit.Second, e.DraggingTime);
if (schedule.WeekViewSettings.NonAccessibleBlockCollection.GetItem<NonAccessibleBlock>(0).StartHour == draggingTime.Hour
|| schedule.WeekViewSettings.NonAccessibleBlockCollection.GetItem<NonAccessibleBlock>(0).StartHour - 1 == draggingTime.Hour && draggingTime.Hour > 0)
{
label.Text = "Cannot be moved to blocked time slots";
}
{% endhighlight %}
{% endtabs %}

### Handle appointment dropping
Using [AppointmentDrop](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDrop_EV.html) event you can get the dropping appointment details, position, time and you can handle whether the appointment can be dropped to the specific position or not. This event will trigger after dropping the appointment. The [AppointmentDropEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDropEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.Appointment.html) - Gets the details of the appointment to be dropped.
[Cancel](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDropEventArgs~Cancel.html) - Appointment dropping can be handled (enable / disable) using this Boolean property.
[DropTime](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentDropEventArgs~DropTime.html) - Gets the dropped time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
var appointment = e.Appointment;
e.Cancel = false;
var dropTime = e.DropTime;
}
{% endhighlight %}
{% endtabs %}

#### Disabling dropping when dropping appointment within the Non-Accessible region
Using `Cancel` property in the `AppointmentDropEventArgs` argument of Schedule `AppointmentDrop` event, you can enable/disable the appointment dropping based on the requirement. In the below, we have disabled the appointment dropping while dropping in the Non-Accessible block region.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
//// Comparing the NonAccessibleBlock Start hour with the dragging time
NSCalendar calendar = NSCalendar.CurrentCalendar;
NSDateComponents dropTime = calendar.Components(NSCalendarUnit.Year |
NSCalendarUnit.Month |
NSCalendarUnit.Day |
NSCalendarUnit.Hour |
NSCalendarUnit.Minute |
NSCalendarUnit.Second, e.DropTime);
if (schedule.WeekViewSettings.NonAccessibleBlockCollection.GetItem<NonAccessibleBlock>(0).StartHour == dropTime.Hour
|| schedule.WeekViewSettings.NonAccessibleBlockCollection.GetItem<NonAccessibleBlock>(0).StartHour - 1 == dropTime.Hour && dropTime.Hour > 0)
{
e.Cancel = true;
}
}
{% endhighlight %}
{% endtabs %}

### Customizing the Drag and Drop environment
Using [DragDropSettings](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings.html) property of schedule, you can handle the behavior of drag and drop in Schedule.

{% tabs %}
{% highlight c# %}
DragDropSettings dragDropSettings = new DragDropSettings();
dragDropSettings.AllowNavigate = true;
dragDropSettings.AllowScroll = false;
var timeSpan = new TimeSpan(0, 0, 0, 1, 0);
dragDropSettings.AutoNavigationDelay = timeSpan;
dragDropSettings.ShowTimeIndicator = true;
dragDropSettings.TimeIndicatorStyle = timeIndicatorStyle;
schedule.DragDropSettings = dragDropSettings;
{% endhighlight %}
{% endtabs %}

#### Disabling navigation when dragging appointment
Using [AllowNavigate](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings~AllowNavigate.html) boolean property can handle the Appointment dragging, whether navigate to next/previous view or not while dragging the appointment to the endpoint of the current view in Schedule. Default value of the `AllowNavigate` property is true and  Schedule will navigate to next/previous view when dragging the appointment the endpoint of the current view.

{% tabs %}
{% highlight c# %}
dragDropSettings.AllowNavigate = false;
{% endhighlight %}
{% endtabs %}

#### Handling navigation delay while holding dragged appointment
Using [AutoNavigationDelay](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings~AutoNavigationDelay.html)  `TimeSpan` property can handle the navigation time when navigating to next/previous view while holding the dragged appointment.

{% tabs %}
{% highlight c# %}
var timeSpan = new TimeSpan(0, 0, 0, 1, 0);
dragDropSettings.AutoNavigationDelay = timeSpan;
{% endhighlight %}
{% endtabs %}

#### Disabling scroll when dragging appointment
Using [AllowScroll](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings~AllowScroll.html) boolean property can handle the Appointment dragging, whether scroll (below/above) the Schedule or not while dragging the appointment to the endpoint of the current view in Schedule. Default value of the `AllowScroll` property is true.

{% tabs %}
{% highlight c# %}
dragDropSettings.AllowScroll = false;
{% endhighlight %}
{% endtabs %}

#### Disabling dragging time indicator
[ShowTimeIndicator](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings~ShowTimeIndicator.html) - Using this boolean property can handle the time indicator whether it should visible or not, which shows the dragged appointment current position time in time text slots. Default value of the `ShowTimeIndicator` property is true.

{% tabs %}
{% highlight c# %}
dragDropSettings.ShowTimeIndicator = false;
{% endhighlight %}
{% endtabs %}

### Customize appearance of dragging Time Indicator
Using [TimeIndicatorStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.DragDropSettings~TimeIndicatorStyle.html) property can handle the time indicator style which contains [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.TimeIndicatorStyle~TextColor.html), [TextSize](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.TimeIndicatorStyle~TextSize.html) and [TextFormat](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.TimeIndicatorStyle~TextFormat.html).

{% tabs %}
{% highlight c# %}
TimeIndicatorStyle timeIndicatorStyle = new TimeIndicatorStyle();
timeIndicatorStyle.TextColor = UIColor.Red;
timeIndicatorStyle.TextSize = 15;
timeIndicatorStyle.TextFormat = (NSString)"hh : mm";
dragDropSettings.TimeIndicatorStyle = timeIndicatorStyle;
schedule.DragDropSettings = dragDropSettings;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/timeindicator.png)

>**Notes**
* While dropping appointment to `AllDay` panel from time slots, appointment start and end time will change to 12.00 AM.
* While dropping appointment to time slots from `AllDay` panel, appointment duration will change as one (1) hour from the dropped time.
* Doesn't support control to control drag and drop.

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

•	[Customize appearance using Style](https://help.syncfusion.com/xamarin-android/sfschedule/data-bindings#customize-appearance-using-style) 
•	[Customize appearance using Event](https://help.syncfusion.com/xamarin-android/sfschedule/data-bindings#customize-appearance-using-event)
•	[Customize appearance using Custom View](https://help.syncfusion.com/xamarin-android/sfschedule/data-bindings#customize-appearance-using-custom-view)

### Customize appearance using Style
Schedule appointment can be customized by setting appointment style properties such as [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~TextColor.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~TextStyle.html), [BorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~BorderColor.html), [BorderCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~BorderCornerRadius.html), [BorderWidth](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~BorderWidth.html) to the `AppointmentStyle` property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
//Creating appointment style
AppointmentStyle appointmentStyle = new AppointmentStyle();
appointmentStyle.TextColor = Color.Red;
appointmentStyle.TextStyle = Typeface.Create("Calibri", TypefaceStyle.Bold);
appointmentStyle.BorderColor = Color.Blue;
appointmentStyle.BorderCornerRadius = 12;
appointmentStyle.BorderWidth = 10;

//Setting appointment style
schedule.AppointmentStyle = appointmentStyle;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/style.png)

### Customize appearance using Event
Schedule appointment can be customized during runtime using [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs.html). `ScheduleAppointment` style can be customized using the `AppointmentStyle` property.

[AppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs.html) has below properties,

•	[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs~Appointment.html) – Contains the appointments values.
•	[AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs~AppointmentStyle.html) – Gets and sets the appointments style.
•	[View](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs~View.html) -  Sets the Custom UI for Appointments.
•	[Bounds](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentLoadedEventArgs~Bounds.html) – Contains the UI bounds of appointment.

{% tabs %}
{% highlight c# %}  
schedule.AppointmentLoaded += schedule_AppointmentLoaded ;

...

private void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs args)
{
    args.AppointmentStyle = new AppointmentStyle();
    
    if(args.Appointment != null && args.Appointment.IsAllDay)
    {
        args.AppointmentStyle.BorderColor = Color.Red;
        args.AppointmentStyle.BorderCornerRadius = 12;
        args.AppointmentStyle.TextColor= Color.White;
        args.AppointmentStyle.BorderWidth = 10;
    }
    else
    {
        args.AppointmentStyle.BorderColor = Color.Blue;
        args.AppointmentStyle.BorderCornerRadius = 12;
        args.AppointmentStyle.TextColor= Color.Red;
        args.AppointmentStyle.BorderWidth = 10;
    }
}
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointmentstyle_event.png)

## Customize appearance using Custom View
Default appointment UI can be changed using `View` property passed through `AppointmentLoadedEventArgs`.

{% tabs %}
{% highlight c# %}
schedule.AppointmentLoaded += schedule_AppointmentLoaded;

...

private void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs args)
{
    if (args.Appointment == null)
        return;
    if(args.Appointment.IsAllDay)
    {
        TextView textView = new TextView(this);
        textView.SetTextColor(Color.Black);
        textView.SetBackgroundColor(GetAndroidColorFromInt(args.Appointment.Color));
        textView.Text = arg.Appointment.Subject;
        arg.View = textView;
    }
    else if (args.Appointment.Subject == "Retrospective")
    {
        ImageButton button = new ImageButton(this);
        button.SetImageResource(Resource.Drawable.Meeting); // Meeting as Image name
        button.SetBackgroundColor(GetAndroidColorFromInt(args.Appointment.Color));
        arg.View = button;
    }
    else
    {
        ImageButton button = new ImageButton(this);
        button.SetImageResource(Resource.Drawable.Cake); // Cake as Image name
        button.SetBackgroundColor(GetAndroidColorFromInt(args.Appointment.Color));
        arg.View = button;
    }
}
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/custom.png)

### Customize Font Appearance

You can change the appearance of Font by setting the [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~TextStyle.html) property of [AppointmentStyle](https://help.syncfusion.com/xamarin-android/sfschedule/data-bindings#appearance-customization) property in Schedule.

{% tabs %}
{% highlight c# %}
 appointmentStyle.TextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");     
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/customfontappointment.png)

Refer [this](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#custom-font-setting-in-xamarinandroid) to configure the custom fonts in Xamarin.Android.


## Selection
Schedule control has built-in events to handle tapped, double tapped and long pressed touch actions.

•	[CellTapped](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs.html)
•	[CellDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs.html)
•	[CellLongPressed](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs.html)

These events will be triggered while perform respective touch actions in timeslots, month cells and in appointments. All the three events contain the same argument [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs.html) which holds selected appointment and date time details in it.

• [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs~SelectedAppointment.html) -  Contains the selected appointment value, it will be null, if any time slots selected.
• [Calendar](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.CellTappedEventArgs~Calendar.html) - Contains selected time slot DateTime value.

{% tabs %}
{% highlight c# %}
schedule.CellTapped += Schedule_CellTapped;
schedule.CellDoubleTapped += Schedule_CellDoubleTapped;
schedule.CellLongPressed += Schedule_CellLongPressed;

...

private void Schedule_CellTapped(object sender, CellTappedEventArgs e)
{
}
private void Schedule_CellDoubleTapped(object sender, CellTappedEventArgs e)
{
}
private void Schedule_CellLongPressed(object sender, CellTappedEventArgs e)
{
}

{% endhighlight %}
{% endtabs %}

### Selection customization
The default selection of an appointment can be customized by using [SelectionBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~SelectionBorderColor.html), [SelectionTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.AppointmentStyle~SelectionTextColor.html) properties in `AppointmentStyle` property of `SfSchedule`. The property is used to customize or override the default selection of the appointments.

N> `BorderWidth` value must be set to highlight `SelectionBorderColor`.

{% tabs %}
{% highlight c# %}
//Creating an appointment style
AppointmentStyle appointmentStyle = new AppointmentStyle();
appointmentStyle.SelectionBorderColor = Color.Yellow;
appointmentStyle.SelectionTextColor = Color.Yellow;

//Setting an appointment style
schedule.AppointmentStyle = appointmentStyle;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/selection.png)

## TimeZone

Schedule allows you to create appointments in various time zones and display them in the user's time zone and any other time zone. Appointments are rendered by recalculating Start and End time based on given time zone.
Consider the following scenario you are in North Carolina and you want to set up a meeting at 10 AM on North Carolina time. You have colleagues in London and Chennai and they also need to participate. The time for this meeting will be 3 PM (15:00) in London and 5.30 AM in Chennai. 
When you each view your calendar, you need to see the appointment displayed relative to your local time zone 5.30 am, 10 am, 3 pm respectively and it can be achieved by setting schedule time zone to default and Appointments time zone to Eastern Standard Time (North Carolina)

If you create all day appointment, then it's start time and end times are set default as 12 am to 12 am so time zone is not applicable for all day appointments

Set schedule to a specific time zone by using "TimeZone" Property of schedule by setting schedule to a default time zone schedule takes that time zone as the local time zone and appointment's start time and end time calculated based on schedule time zone

    {%tabs%}
    {% highlight c# %}
    schedule.TimeZone = "GMT Standard Time";
    {% endhighlight %}
    {% endtabs %}

### Creating Appointment's in different Timezone
Set Appointment to specif time zone using StartTimeZone and EndTimeZone property of the Appointment the appointment's start time and end time calculated based the given time zone information for start time and end time, you can give different time zone's for start time and end time property.
Use ActualStartTime and ActualEndTime Property to get the exact Local Start Time and End Time of the appointment

    {%tabs%}
    {% highlight c# %}
    appointment.StartTimeZone = "India Standard Time";
	appointment.EndTimeZone = "India Standard Time";
	 
	Calendar localStartTime = appointment.ActualStartTime;
	Calendar localEndTime = appointment.ActualEndTime;
    {% endhighlight %}
    {% endtabs %}

>**NOTE**
* If the recurring appointment is converted to another time zone then the whole sequence is recalculated according to the new time zone information
* Custom Appointment supported for ScheduleAppointment's StartTimeZone and EndTimeZone properties
* After rescheduling an appointment using drag and drop, if ScheduleTimeZone has set then the appointment's start time and end time recalculated based on Schedule Time Zone. Otherwise, the appointment's start time and end time recalculated based on Local Time Zone.
Schedule's ActualStartTime and ActualEndTime properties has the local start time and local end time of the appointment.

For an example,consider, your local time zone is IndianStandardTime and appointment's start time zone and end time zone has set as default, if you drag an appointment from 9 AM and drop this on 1 PM and you set the schedule Time zone as AUS Central Time Zone (Darwin) then the appointment's start time and end time will be calculated from the schedule time zone and the appointment will be rendered on 5 PM on your schedule,
if you don't set the schedule Time Zone and it was set as default then the appointment rendered based on the device local time zone.
