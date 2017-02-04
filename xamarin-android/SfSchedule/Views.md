---
layout: post
title: Types of Schedule Views.
description: How to create Views in Schedule control.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Views

Schedule control provides four different types of views to display dates. Day view, Week view, Work Week view and Month view. It can be assigned to the schedule control by using `ScheduleView` property. Based on the user’s preference appointments can be viewed in any of the four type of view available. By default schedule control is assigned with day view.

## Day View

Day view is used to display a single day; current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.DayView;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img1.jpeg)

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `DayLabelSettings` of  `DayViewSettings` and the size of those strings are also customizable.

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.WorkStartHour=10;
	dayViewSettings.WorkEndHour=18;
	sfschedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `DayViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.DayView;

	//setting non-accessing blocks.
	NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
	NonAccessibleBlock lunchHour = new NonAccessibleBlock();
	lunchHour.StartTime=13;
	lunchHour.EndTime=14;
	lunchHour.Color=Color.Black;
	lunchHour.Text="LUNCH";
	nonAccessibleBlocksCollection.Add(lunchHour);
	dayViewSettings.NonAccessibleBlocks=nonAccessibleBlocksCollection;
	sfschedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Working Hours

You can modify the working hours using `WorkStartHour` and `WorkEndHour` properties of `DayViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.WorkStartHour = 10;
	dayViewSettings.WorkEndHour = 18;
	sfschedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of DayViewSettings as true.Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`. To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.ShowAllDay=true;
	sfschedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img2.jpeg)

>**Note**:These properties and customizations are applicable only for Day View. Customizations for other views are discussed under the respective views.

## Week View

To view all the seven days of a particular week, by default if will be current week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WeekView;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img3.jpeg)

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WeekLabelSettings` of `WeekViewSettings` and the size of those strings are also customizable.

Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WeekView;

	//setting label size and formats
	WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
	weekLabelSettings.TimeLabelSize = 14;
	weekLabelSettings.DateLabelSize = 25;
	weekLabelSettings.DateFormat = "dd ";
	weekLabelSettings.DayFormat = "EEEE";
	weekLabelSettings.TimeFormat = "hh:mm a ";
	weekViewSettings.WeekLabelSettings = weekLabelSettings;
	sfschedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `WeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WeekView;

	//setting non-accessing blocks.
	NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
	NonAccessibleBlock lunchHour = new NonAccessibleBlock();
	lunchHour.StartTime=13;
	lunchHour.EndTime=14;
	lunchHour.Color=Color.Black;
	lunchHour.Text="LUNCH";
	nonAccessibleBlocksCollection.Add(lunchHour);
	weekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;

	sfschedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour` properties of `WeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings ();
	weekViewSettings.WorkStartHour = 10;
	weekViewSettings.WorkEndHour = 18;
	sfschedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### All Day Appointments Panel

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WeekViewSettings` as true. Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.ShowAllDay = true;

	sfschedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img4.jpeg)

## Work Week View

To view working days of a particular week, by default current work week will be displayed. Saturday and Sunday are the non-working days by default; it can be customized with any days in a week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WorkWeekView;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img5.jpeg)

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WorkWeekLabelSettings` of  `WorkWeekViewSettings` and the size of those strings are also customizable.Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WorkWeekView;
	//setting label size and formats
	WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
	workWeekLabelSettings.TimeLabelSize = 14;
	workWeekLabelSettings.DateLabelSize = 25;
	workWeekLabelSettings.DateFormat = "dd ";
	workWeekLabelSettings.DayFormat = "EEEE";
	workWeekLabelSettings.TimeFormat = "hh:mm a ";
	workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;

	sfschedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `WorkWeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting non-accessing blocks.
	NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
	NonAccessibleBlock lunchHour = new NonAccessibleBlock();
	lunchHour.StartTime=13;
	lunchHour.EndTime=14;
	lunchHour.Color=Color.Black;
	lunchHour.Text="LUNCH";
	nonAccessibleBlocksCollection.Add(lunchHour);
	workWeekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;

	sfschedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour`  properties of `WorkWeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();	
	workWeekViewSettings.WorkStartHour = 10;
	workWeekViewSettings.WorkEndHour = 18;
	sfschedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WorkWeekViewSettings` as true. Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of All day appointment panel refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.ShowAllDay = true;
	sfschedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Non-Working Days

You can view the working days alone by restricting the non working days using `NonWorkingDays` property in `Schedule`.

![](Views_images/Views_img6.jpeg)

## Month View

To view entire dates of a particular month, by default current month will be displayed initially. Appointments arranged within the cell based on its duration. Current date is differentiated by some color and rest of the dates in a month will be in different color., Also the color differentiation for dates will be applicable for previous and next month dates.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.MonthView;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

![](Views_images/Views_img7.jpeg)

### Inline

#### Show Appointments Inline 

By enabling Inline feature in month view, while touch the month view cell, appointments available in a particular day will be listed in inline view. 

{% highlight c# %}

	SfSchedule sfschedule = new SfSchedule(this);
	sfschedule.ScheduleView = ScheduleView.WeekView;

	//setting Show inline 
	sfchedule.MonthViewSettings.ShowAppointmentsInline = true;

{% endhighlight %}

#### Inline View Customization

By enabling the Inline view feature, while tap on the schedule month view cell it will open a inline view which can be customized accordingly. To know more about Inline view customization of Month cell refer [View Customization](/xamarin-android/sfschedule/Appearance-and-Styling "View Customization").

#### Inline Appointment Customization

By enabling the Inline view feature, while tap on the schedule month view cell it will open a inline view which contains list of appointments on a particular day.You can customize the inline appointments. To know more about Inline appointment customization of Month cell refer [View Customization](/xamarin-android/sfschedule/Appearance-and-Styling "View Customization").

#### InlineAppointmentTapped Event

You can able to know the details of appointments in inline using `InlineAppointmentTapped` event in `Schedule`. Details of the selected  appointment and the corresponding date is passed through `InlineAppointmentTappedEventArgs` as `selectedAppointment` and `selectedDate` respectively.

{% highlight C# %}

	monthViewSettings.InlineAppointmentTappedEvent += (object sender, MonthViewSettings.InlineAppointmentTappedEventArgs e) =>
	{
	var appointment = e.P2;
	var date = e.P1;
	};

{% endhighlight %}

### Month Navigation Direction

`MonthView` of Schedule can be navigated horizontally and vertically.You can change the direction of navigation through `MonthNavigationDirection` property of `MonthViewSettings`.By default MonthNavigation value is `Horizontal`

{% highlight C# %}

	MonthViewSettings monthViewSettings = new MonthViewSettings();
	//To navigate vertically
	monthViewSettings.MonthNavigationDirection =  MonthNavigationDirections.Vertical;
	sfschedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `MonthLabelSettings` of  `MonthViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();

	//setting label size and formats
	MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
	monthLabelSettings.DayLabelSize=10;
	monthLabelSettings.DayFormat="E";
	monthLabelSettings.DateLabelSize=26;
	monthLabelSettings.DateFormat="dd";
	monthViewSettings.MonthLabelSettings = monthLabelSettings;
	sfschedule.MonthViewSettings = monthViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Blackout dates

You can restrict/allocate certain month cell as blackout days using `BlackoutDates` of `MonthViewSettings`, so that we can allocate those cells for predefined events/activities like Scheduled maintenance, planned leave etc.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();

	//setting black out dates
	List<Calendar> blackDatesCollection = new List<Calendar>();
	Calendar currentDate = Calendar.Instance;
	Calendar firstDate = (Calendar)currentDate.Clone();
	firstDate.Set(
	currentDate.Get(CalendarField.Year),
	currentDate.Get(CalendarField.Month),
	21// currentDate.Get(CalendarField.DayOfMonth),
	);
	blackDatesCollection.Add(firstDate);
	Calendar secondDate = (Calendar)currentDate.Clone();
	secondDate.Set(
	currentDate.Get(CalendarField.Year),
	currentDate.Get(CalendarField.Month), 22
	);
	blackDatesCollection.Add(secondDate);
	Calendar thirdDate = (Calendar)currentDate.Clone();
	thirdDate.Set(
	currentDate.Get(CalendarField.Year),
	currentDate.Get(CalendarField.Month),
	23
	);
	blackDatesCollection.Add(thirdDate);
	monthViewSettings.BlackoutDates = blackDatesCollection;

	sfschedule.MonthViewSettings = monthViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Week number

You display the week number of the year in month view by setting `ShowWeekNumber` in property of `MonthViewSettings` are true. By default it is false.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.ShowWeekNumber=true;
	sfschedule.MonthViewSettings = monthViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

#### Visible AppointmentCount

You can customize the number of appointments to be rendered inside a month view cell using `VisibleCellAppointmentsCount` property of `MonthViewSettings`

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfschedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.VisibleCellAppointmentsCount = 10;
	sfschedule.MonthViewSettings = monthViewSettings;
	
	// Set our view from the "main" layout resource
	SetContentView(sfschedule);

{% endhighlight %}

### Month cell customization

You can customize the month cells of MonthView using vaious properties of `MonthCellStyle`. To know more about customization of MonthView refer [View Customization](/xamarin-android/sfschedule/appearance-and-styling "View Customization")

![](Views_images/Views_img8.jpeg)