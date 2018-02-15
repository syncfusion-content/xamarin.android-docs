---
layout: post
title: Localization of Schedule
description: How to Localize the contents of Schedule control.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Localization 

Schedule control is available with complete localization support. Localization can be specified by setting the [Locale](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfschedule/Syncfusion.SfSchedule.Android~Com.Syncfusion.Schedule.SfSchedule~Locale.html) property of SfSchedule. In the format of `Language code`.

## Change default control language

Based on the `Locale` specified the strings in the control such as Date, time, days are localized accordingly.

By default, schedule control is available with en locale, which is English.


{% highlight c# %}   
    
          //creating new instance for schedule
            SfSchedule schedule = new SfSchedule(this);
          //setting schedule view
            schedule.ScheduleView = ScheduleView.DayView;
          //setting locale for the control
            schedule.Locale = new Locale("fr");
 
{% endhighlight %}   
   

>**Note:** AM/PM in the timeline will not be localized in the Schedule views

![](Localization_images/Localization.png)   

## Change custom texts in the control.

You can localize the custom strings used in the schedule control. You can localize custom text available in the control by adding equivalent localized string in the string.xml file.

 
{% highlight xml %} 
       
     <resources>
    	<string name="No_Appointments">Aucun événement</string>
     	<string name="all_day">Toute la journée</string>
     </resources>
	 
{% endhighlight %}   

Android can select and load resources from different directories, based on the device configuration and locale, refer [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Localization_Android-352507966.zip). For an example, if an application requires multiple languages we can follow the below steps.

The procedure for creating strings.xml files is as follows:

*	Translate the strings.xml file to each language.
*	Create new folders under resource as values-`ar`, values-`de`, values-`en` and values-`fr` (The original values folder already exists).
*	Place the translated strings.xml files in the respective folders.

![](Localization_images/localization_img2.jpeg)

>**Note:** The corresponding values folder loads only depends on the device configuration and locale.
