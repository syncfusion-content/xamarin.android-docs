---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.Android
description: Learn how to change the view mode for calendar
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Built-in Views

SfCalendar control provides two types of views to display dates such as month view and year view. It can be assigned to the SfCalendar control by using view mode property.

By default SfCalendar control is assigned with month view. Based on the user’s preference, SfCalendar can be viewed in any one of the available two type.


## MonthView

This displays entire dates of a particular month, by default current month will be displayed on Loading. The current date is provided with seperate color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);

sfCalendar.ViewMode = ViewMode.MonthView;

{% endhighlight %}

![](images/month_view.png)                                        


### Month View Settings

* The current day text color can be modified using `TodayTextColor` 
* The month view label settings class has the APIs to change date text size, day text size and various format options. 
* The Background color of the inline view can be modified using `InlineBackgroundColor` property.
* The blackout date color can be modified with `BlackoutColor` Property. 

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);

MonthViewLabelSetting labelSettings = new MonthViewLabelSetting();
labelSettings.DateFormat = "dd";
labelSettings.DayLabelSize = 20;
labelSettings.DayFormat = "EEE";
labelSettings.DateLabelSize = 12;

MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.TodayTextColor = Android.Graphics.Color.ParseColor("#1B79D6");
monthViewSettings.InlineBackgroundColor = Android.Graphics.Color.ParseColor("#E4E8ED");
monthViewSettings.WeekEndBackgroundColor=Android.Graphics.Color.ParseColor("#F7F7F7");
monthViewSettings.MonthViewLabelSetting = labelSettings;

sfCalendar.MonthViewSettings = monthViewSettings;

{% endhighlight %}

N> Similarly there are many settings available to modify Text and Background colors of month view in `MonthViewSettings` class.

## YearView

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The Years can be changed by swiping back and forth or `forward` and `backward` methods can be used. The Months can be navigated quickly by selecting on the particular month in year view.

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);

sfCalendar.ViewMode = ViewMode.YearView;

{% endhighlight %}

![](images/year_view.png)                                        


### Year View Settings

*	The Month header color can be modified using `MonthHeaderTextColor` property in similar way, year header and date text color can be changed using `YearTextColor` and `DateTextColor` properties respectively. 
*	The gravity of the month name can be modified using `LabelAlignment` property, to position it to Left, Right or Center. 
*	The complete layout’s background color can be modified using `YearLayoutBackground` property.

{% highlight c# %}

YearViewSettings yearViewSettings = new YearViewSettings();
yearViewSettings.YearHeaderTextColor = Android.Graphics.Color.ParseColor("#1B79D6");
yearViewSettings.MonthHeaderBackground = Android.Graphics.Color.ParseColor("#E4E8ED");
yearViewSettings.DateTextColor = Android.Graphics.Color.Red;
yearViewSettings.HeaderLabelAlignment = LabelAlignment.Center;
sfCalendar.YearViewSettings = yearViewSettings;

{% endhighlight %}


