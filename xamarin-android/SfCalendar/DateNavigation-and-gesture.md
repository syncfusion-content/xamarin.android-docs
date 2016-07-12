---
layout: post
title: Date Navigation and Gestures with Syncfusion Calendar control for Xamarin.Android
description: Learn the complete navigation and gestures support
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Date Navigation and Gestures

## Forward

By default, the date can be navigated to next view using touch gesture and swiping the control in right to left direction. The view can also be changed programmatically using `forward` method available in SfCalendar. It will move to next month, if the view mode is month or it will move to next Year,if the view mode is year.

{% highlight c# %}

	calendar.Forward();

{% endhighlight %}

N> It can be navigated until it reaches the MaxDate

## Backward

By default, the date can be navigated to previous view using touch gesture and swiping the control in left to right direction. The view also can be changed programmatically using `backward` method available in SfCalendar. It will move to previous month, if the view mode is month or it will move to previous year, if view mode is year view.

{% highlight c# %}

	calendar.Backward();

{% endhighlight %}

N> It can be navigated until it reaches the MinDate.

## Move to Date 

Visible dates can be moved to specific date using `MoveToDate` property available in SfCalendar. It will move to any specific month if the view mode is month view or move to year if it is a year view.

{% highlight c# %}

	Calendar moveToDate = Calendar.getInstance();   
    moveToDate.Set
        (
                2010,
                Calendar.AUGUST,
                25,
                0,
                0,
                0
        );
    calendar.MoveToDate=moveToDate;


{% endhighlight %}

N>  The specified date should lie between MinDate and MaxDate, if the specified date is greater than MaxDate then the view will be moved to maxDate and if the specified date is lesser than the MinDate then the view will be moved to minDate.

## Toggle  navigation

By default, calendar views can be moved backwards and forwards using touch swipe gesture. This navigation, using touch gesture can be enabled and disabled using `NavigationEnabled` property available in SfCalendar control. By default, `NavigationEnabled` property is enabled.

{% highlight c# %}

	calendar.ViewMode=ViewMode.MonthView;
	calendar.NavigationEnabled=false;
	
{% endhighlight %}

## Transition modes

Dates can be navigated by using swipe gesture as well as using inbuilt methods `forward` and `backward`. By default those navigation are performed along with Scroll animation. Other than the default scroll animation, there are other options available like card, reveal, float animations. It can be changed by using  TransitionMode property of SfCalendar control.

{% highlight c# %}

    calendar.TransitionMode=TransitionMode.Card;
	
{% endhighlight %}


