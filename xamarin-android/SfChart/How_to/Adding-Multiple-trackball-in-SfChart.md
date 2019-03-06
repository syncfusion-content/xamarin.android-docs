---
layout: post
title: Adding Multiple trackball in Syncfusion SfChart
description: Adding Multiple trackball in SfChart
platform: Android
control: Chart
documentation: ug
---

## Adding Multiple trackball in SfChart

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.SfChart.html) allows the user to activate multiple trackballs in chart area by adding two instances of trackball behavior to chart and by using the [`Show`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfChart.Android~Com.Syncfusion.Charts.ChartTrackballBehavior~Show.html) method. Each trackball will be interacting separately by using [`HitTest`] method which returns the nearest trackball that contains the touch point and the touch override methods of trackball behavior, but these Multiple trackballs having effect only when the [`ActivationMode`] is set as [`None`]. 

The following code sample demonstrates this:

{% highlight c# %}

TrackballBehaviorExt trackballBehavior1 = new TrackballBehaviorExt();
trackballBehavior1.ActivationMode = ChartTrackballActivationMode.None;
chart.Behaviors.Add(trackballBehavior1);

TrackballBehaviorExt trackballBehavior2 = new TrackballBehaviorExt();
trackballBehavior2.ActivationMode = ChartTrackballActivationMode.None;
chart.Behaviors.Add(trackballBehavior2);

{% endhighlight %}

{% highlight c# %}

trackballBehavior1.Show(pointX, pointY);
trackballBehavior2.Show(pointX, pointY);

{% endhighlight %}

{% highlight c# %}

public class TrackballBehaviorExt : ChartTrackballBehavior
{
   bool isActivate = false;

   protected override void OnTouchDown(float pointX, float pointY)
   {
       if (HitTest(pointX, pointY))
       {
          isActivate = true;
          base.OnTouchDown(pointX, pointY);
       }
   }

   protected override void OnTouchMove(float pointX, float pointY)
   {
      if (isActivate)
      {
         Show(pointX, pointY);
         base.OnTouchMove(pointX, pointY);
      }
   }

   protected override void OnTouchUp(float pointX, float pointY)
   {
       isActivate = false;
   }
}

{% endhighlight %}