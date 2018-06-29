---
layout: post
title: Segments
platform: Xamarin.Android
control: ProgressBar
documentation: ug
---
# Segments

To visualize the progress of multiple sequential tasks, split the progress bar into multiple segments by setting the [`SegmentCount`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfProgressBar.Android~Syncfusion.Android.ProgressBar.ProgressBarBase~SegmentCount.html) property, as shown in the following code example.

{% highlight c# %}

// Using linear progress bar.
SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar(this); 
sfLinearProgressBar.SegmentCount = 4;

// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar(this);  
circularProgressBar.SegmentCount = 7;

{% endhighlight %} 

![](overview_images/Segment.png)

**Gap** **Customization**

You can also customize the default spacing between the segments using the [`GapWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfProgressBar.Android~Syncfusion.Android.ProgressBar.ProgressBarBase~GapWidth.html) property, as shown in following code example.

{% highlight c# %}
// Using linear progress bar.
SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar(this); 
sfLinearProgressBar.GapWidth = 5;

// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar(this);  
circularProgressBar.GapWidth = 10;

{% endhighlight %}

{% endtabs %} 

![](overview_images/Gap.png)