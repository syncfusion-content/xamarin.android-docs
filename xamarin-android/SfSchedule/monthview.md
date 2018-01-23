---   
layout: post   
title: MonthView   
description: Overview of MonthView related features
platform: xamarin.android   
control: SfSchedule   
documentation: ug   
---   
    
# Month View
`MonthView` of `SfSchedule` used to display entire dates of the specific month, current month will be displayed by default initially. Current date color is differentiated with other dates of the current month, also the color differentiation for dates will be applicable for previous and next month dates.

{% tabs %}
{% highlight c# %}

			schedule.ScheduleView = ScheduleView.MonthView;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthview.png)

## Month Appointment indicator
In `MonthView`, appointments are not viewed in the month cell instead appointment indicators are drawn. You can customize the number of appointment indicators displayed in month cell using  [AppointmentIndicatorCount](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~AppointmentIndicatorCount.html) property of [MonthViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings.html) in `SfSchedule`, by default Appointment indicator count is 3.

{% highlight c# %}

			//creating new instance for MonthViewSettings
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			monthViewSettings.AppointmentIndicatorCount = 2;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

![](monthview_images/appointmentindicator.png)

>**Notes**: If appointments count are lesser than the AppointmentIndicatorCount value in the particular day, then according to number of appointments available, indicator will be displayed in the month cell.Maximum number of appointment indicators drawn in the month cell is 6.   

## Month Inline View
You can use [ShowAppointmentsInline](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~ShowAppointmentsInline.html) bool property in [MonthViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings.html) to enable / disable the month inline view, by setting `ShowAppointmentsInline` property as `true` you can view the Appointments in the specific date. 

{% highlight c# %}

			//creating new instance for MonthViewSettings
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			monthViewSettings.ShowAppointmentsInline = true;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

![](monthview_images/appointmentindicator.png)

>**Notes**: If appointments not there in the selected day, Inline view displays the text as "No Events"      

## Month Navigation direction
MonthView of Schedule can be navigated in both horizontal and vertical direction. You can change the direction of navigation through [MonthNavigationDirection](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~MonthNavigationDirection.html) property of `MonthViewSettings` in `SfSchedule`, by default Month navigation direction is `Horizontal`.

{% tabs %}
{% highlight c# %}

			monthViewSettings.MonthNavigationDirection = MonthNavigationDirections.Vertical;

{% endhighlight %}
{% endtabs %}

## Restricted days in Month
You can disable the interaction for certain date in Month view by using [BlackoutDates](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~BlackoutDates.html) of `MonthViewSettings`, using this you can allocate / restrict the specific date for predefined events.

{% tabs %}
{% highlight c# %}

			//creating new instance for MonthViewSettings 
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			//setting black out dates
			ObservableCollection<Calendar> blackoutDateCollection = new ObservableCollection<Calendar>();

			Calendar currentDate = Calendar.Instance;
			Calendar blockedDate1 = (Calendar)currentDate.Clone();
			blockedDate1.Set(currentDate.Get(CalendarField.Year),
							 currentDate.Get(CalendarField.Month),
							 currentDate.Get(CalendarField.Date) + 1);

			Calendar blockedDate2 = (Calendar)currentDate.Clone();
			blockedDate2.Set(currentDate.Get(CalendarField.Year),
							 currentDate.Get(CalendarField.Month),
							 currentDate.Get(CalendarField.Date) + 2);

			Calendar blockedDate3 = (Calendar)currentDate.Clone();
			blockedDate3.Set(currentDate.Get(CalendarField.Year),
							 currentDate.Get(CalendarField.Month),
							 currentDate.Get(CalendarField.Date) + 3);

			blackoutDateCollection.Add(blockedDate1);
			blackoutDateCollection.Add(blockedDate2);
			blackoutDateCollection.Add(blockedDate3);
			monthViewSettings.BlackoutDates = blackoutDateCollection;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/blackoutdate.png)

## First day of Week in Month
You can set First day of week using [FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~FirstDayOfWeek.html) property of `SfSchedule`, by default schedule control will rendered with `Sunday` as the first day of the week. 

{% tabs %}
{% highlight c# %}

			//setting FirstDayOfWeek
			schedule.FirstDayOfWeek = 2; // Monday

{% endhighlight %}
{% endtabs %}

![](monthview_images/firstdayofweek.png)

## Week Number of the Year in Month
You can display the Week Number of the year in Month View by setting [ShowWeekNumber](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~ShowWeekNumber.html) property of `MonthViewSettings` as `true`, by default it is `false`.

{% tabs %}
{% highlight c# %}

			monthViewSettings.ShowWeekNumber = true;

{% endhighlight %}
{% endtabs %}

![](monthview_images/showweeknumber.png)

## Week Number Appearance
You can customize the Week Number appearance by using [WeekNumberStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~WeekNumberStyle.html) property of `MonthViewSettings`. Week number [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.WeekNumberStyle~BackgroundColor.html), [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.WeekNumberStyle~TextColor.html), [TextSize](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.WeekNumberStyle~TextSize.html) and [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.WeekNumberStyle~TextStyle.html) can be customized using `WeekNumberStyle` properties.

{% tabs %}
{% highlight c# %}

			//creating new instance for WeekNumberStyle
			WeekNumberStyle weekNumberStyle = new WeekNumberStyle();
			weekNumberStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
			weekNumberStyle.BackgroundColor = Color.Blue;
			weekNumberStyle.TextColor = Color.White;
			weekNumberStyle.TextSize = 12;
			monthViewSettings.WeekNumberStyle = weekNumberStyle;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/weeknumberstyle.png)

## Month Label Formatting 
You can change the Format of the Month date and day labels string in the Schedule using [DateFormat](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthLabelSettings~DateFormat.html), [DayFormat](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthLabelSettings~DayFormat.html) and [DateLabelSize](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthLabelSettings~DateLabelSize.html) properties of [MonthLabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthViewSettings~MonthLabelSettings.html) in `MonthViewSettings`. 

{% tabs %}
{% highlight c# %}

			//creating new instance for MonthLabelSettings
			MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
			monthLabelSettings.DayFormat = "EEEE";
			monthLabelSettings.DateFormat = "dd";
			monthLabelSettings.DateLabelSize = 15;
			monthViewSettings.MonthLabelSettings = monthLabelSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthlabelformat.png)

## View Header Appearance  
You can customize the View Header appearance by using [ViewHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ViewHeaderStyle.html) property in SfSchedule. View Header [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ViewHeaderStyle~BackgroundColor.html), [DayTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ViewHeaderStyle~DayTextColor.html), [DayTextSize](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ViewHeaderStyle~DayTextSize.html) and [DayTextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.ViewHeaderStyle~DayTextStyle.html) can be customized using `ViewHeaderStyle` properties.

{% tabs %}
{% highlight c# %}

			//creating new instance for viewHeaderStyle 
			ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
			viewHeaderStyle.DayTextStyle = Typeface.Create("Arial", TypefaceStyle.Italic);
			viewHeaderStyle.DayTextSize = 15;
			viewHeaderStyle.DayTextColor = Color.White;
			viewHeaderStyle.BackgroundColor = Color.Blue;
			schedule.ViewHeaderStyle = viewHeaderStyle;

{% endhighlight %}
{% endtabs %}

![](monthview_images/viewheaderstyle.png)

## MonthCell Appearance 
You can customize the Month view cell in three ways,

* [Customize month cell using style](#customize-month-cell-using-style)
* [Customize month cell using event](#customize-month-cell-using-event)
* [Customize month cell with custom UI](#customize-month-cell-with-custom-ui)

### Customize month cell using style
By using [MonthCellStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle.html) of `SfSchedule` you can customize the month cell properties such as [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~BackgroundColor.html), [NextMonthBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~NextMonthBackgroundColor.html), [NextMonthTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~NextMonthTextColor.html), [PreviousMonthBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~PreviousMonthBackgroundColor.html), [PreviousMonthTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~PreviousMonthTextColor.html), [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~TextColor.html), [TextSize](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~TextSize.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~TextStyle.html), [TodayBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~TodayBackgroundColor.html) and [TodayTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellStyle~TodayTextColor.html).
   
{% tabs %}
{% highlight c# %}

			//creating new instance for MonthCellStyle 
            MonthCellStyle monthCellStyle = new MonthCellStyle();
			monthCellStyle.TextSize = 15;
			monthCellStyle.TextColor = Color.White;
			monthCellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
			monthCellStyle.BackgroundColor = Color.Blue;
			monthCellStyle.TodayTextColor = Color.White;
			monthCellStyle.TodayBackgroundColor = Color.Red;
			monthCellStyle.PreviousMonthTextColor = Color.White;
			monthCellStyle.PreviousMonthBackgroundColor = Color.LightGray;
			monthCellStyle.NextMonthTextColor = Color.White;
			monthCellStyle.NextMonthBackgroundColor = Color.LightGray;
			schedule.MonthCellStyle = monthCellStyle;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellstyle.png)
    
### Customize month cell using event
By using [MonthCellLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~MonthCellLoaded_EV.html) event in `SfSchedule`, you can customize the month cell properties in the run time. In `MonthCellLoaded` event, arguments such as [CellStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~CellStyle.html), [Appointments](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~Appointments.html), [Calendar](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~Calendar.html), [Bounds](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~Bounds.html), [View](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~View.html) and boolean properties such as [IsToday](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~IsToday.html), [IsNextMonthDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~IsNextMonthDate.html), [IsPreviousMonthDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~IsPreviousMonthDate.html) and [IsBlackOutDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~IsBlackoutDate.html) are in the [MonthCellLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html). 

{% tabs %}
{% highlight c# %}

			schedule.MonthCellLoaded += Schedule_MonthCellLoaded;
			...
			void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
		{
			if (e.IsToday)
			{
				e.CellStyle.TextSize = 15;
				e.CellStyle.BackgroundColor = Color.Red;
				e.CellStyle.TextColor = Color.White;
				e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Bold);
			}
			else if (e.IsNextMonthDate)
			{
				e.CellStyle.TextSize = 12;
				e.CellStyle.BackgroundColor = Color.White;
				e.CellStyle.TextColor = Color.Gray;
				e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Normal);
			}
			else if (e.IsPreviousMonthDate)
			{
				e.CellStyle.TextSize = 12;
				e.CellStyle.BackgroundColor = Color.White;
				e.CellStyle.TextColor = Color.Gray;
				e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Normal);
			}
			else if (e.IsBlackoutDate)
			{
				e.CellStyle.TextSize = 15;
				e.CellStyle.BackgroundColor = Color.Black;
				e.CellStyle.TextColor = Color.White;
				e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Bold);
			}
			else
			{
				e.CellStyle.TextSize = 15;
				e.CellStyle.BackgroundColor = Color.Blue;
				e.CellStyle.TextColor = Color.White;
				e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
			}
		}


{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellstyle_event.png)

#### Customize month cell with custom UI 
You can set the Custom UI for the month cell using [View](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthCellLoadedEventArgs~View.html) property of `MonthCellLoadedEventArgs` in the `MonthCellLoaded` event of `SfSchedule`.

{% tabs %}
{% highlight c# %}

			schedule.MonthCellLoaded += Schedule_MonthCellLoaded;
			...
			void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
		{
			Button button = new Button(this);
			button.Text = e.Calendar.Time.GetDate().ToString();
			button.SetTextColor(Color.White);
			button.SetBackgroundColor(Color.Blue);
			e.View = button;
			if (e.IsToday)
			{
				button.SetBackgroundColor(Color.Red);
				button.SetTextColor(Color.White);
			}
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellcustomview.png)

## Getting Inline Appointment details
Using [ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineAppointmentTappedEventArgs~ScheduleAppointment.html) argument in the [MonthInlineAppointmentTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineAppointmentTappedEventArgs.html) of [MonthInlineAppointmentTapped](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~MonthInlineAppointmentTapped_EV.html) event, you can get the details Month Inline Appointments details while tapping the specific appointment. You can do the required functions while tapping the inline appointment using this event. 

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineAppointmentTapped += Schedule_MonthInlineAppointmentTapped;
			...
			void Schedule_MonthInlineAppointmentTapped(object sender, MonthInlineAppointmentTappedEventArgs e)
		{
			var appointment = (e.ScheduleAppointment as ScheduleAppointment);
			Toast.MakeText(this, appointment.Subject + " * " + appointment.StartTime.Time.ToString(), ToastLength.Long).Show();
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlineappointmentdetails.png)

## InlineView Appearance  
By using [MonthInlineLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~MonthInlineLoaded_EV.html) in `SfSchedule`, you can customize the month inline view properties in the run time. In `MonthInlineLoadedEvent`, arguments such as [MonthInlineViewStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineViewStyle.html), [Appointments](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineLoadedEventArgs~Appointments.html) and [Calendar](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineLoadedEventArgs~Calendar.html) are in the MonthInlineLoadedEventArgs.

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineLoaded += Schedule_MonthInlineLoaded;
			...
			void Schedule_MonthInlineLoaded(object sender, MonthInlineLoadedEventArgs e)
		{
			MonthInlineViewStyle monthInlineViewStyle = new MonthInlineViewStyle();
			monthInlineViewStyle.TextSize = 20;
			monthInlineViewStyle.BackgroundColor = Color.Blue;
			monthInlineViewStyle.TextColor = Color.Green;
			monthInlineViewStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
			monthInlineViewStyle.TimeTextColor = Color.Red;
			monthInlineViewStyle.TimeTextSize = 12;
			monthInlineViewStyle.TimeTextFormat = "hh a";
			e.MonthInlineViewStyle = monthInlineViewStyle;
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlineviewstyle.png)

## Inline Appointment Appearance 
You can customize the Month inline view Appointment by using [MonthInlineAppointmentLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~MonthInlineAppointmentLoaded_EV.html) in `SfSchedule`, using [View](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs~View.html) of [MonthInlineAppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs.html) argument. You can get the details of Appointment in the [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs~Appointment.html) argument.

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineAppointmentLoaded += Schedule_MonthInlineAppointmentLoaded;
			...
			void Schedule_MonthInlineAppointmentLoaded(object sender, MonthInlineAppointmentLoadedEventArgs e)
		{
			var appointment = (e.Appointment as ScheduleAppointment);
			Button button = new Button(this);
			button.Text = "Appointment :" + appointment.Subject;
			button.SetBackgroundColor(Color.Blue);
			button.SetTextColor(Color.White);
			e.View = button;
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlinecustomview.png)


