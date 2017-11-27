---
layout: post
title: Built-in customizations | SfPullToRefresh | Xamarin.Android | Syncfusion
description: Built-in customizations in SfPullToRefresh
platform: Xamarin.Android
control: SfPullToRefresh
documentation: ug
--- 

# Built-in Customizations

This section gives a quick overview of the various built-in customizations supported by SfPullToRefresh.

## Property Settings

The various properties of SfPullToRefresh are listed below:

* [TransitionType](#transitiontype)
* [RefreshContentThreshold](#refreshcontentthreshold)
* [PullingThreshold](#pullingthreshold)
* [RefreshContentRadius](#refreshcontentradius)
* [ProgressStrokeWidth](#progressstrokewidth)
* [ProgressStrokeColor](#progressstrokecolor)
* [ProgressBackgroundColor](#progressbackgroundcolor)
* [ProgressShadowColor](#progressshadowcolor)
* [Progress](#progress)
* [IsRefreshing](#isrefreshing)

### TransitionType

In the `TransitionType.SlideOnTop`, the progress view will render over the pullable content and it will be moved based on the pulling position, whenever the pulling action is performed. 

In the `TransitionType.Push`, the progress view will push the pullable content down, simultaneously moving the progress view and the pullable content based on the pulling position, whenever the pulling action is performed. 

Refer the below code example to switch to the `TransitionType.Push` mode of transition.

{% highlight c# %}

pullToRefresh.TransitionType = TransitionType.Push;

{% endhighlight %}

### RefreshContentThreshold

The [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) serves different purpose based on the [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~TransitionType.html) which is explained in the below table: 

<table width = "550">
<tr>
<th width="25%">TransitionType</th>
<th width="75%">Purpose</th>
</tr>
<tr>
<td width="25%">SlideOnTop</td>
<td width="75%"> It denotes the starting Y-position of the progress view in the application.</td>
</tr>
<tr>
<td width="25%">Push</td>
<td width="75%"> It denotes the Y-point after which pulling will be recognized.</td>
</tr>
</table>

The default value of [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) is 25.

N> For both the transition types, the progress view will be rendered in the application at [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) property, when the refreshing animation is in progress.

Refer the below code example to set the [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) property.

{% highlight c# %}

pullToRefresh.RefreshContentThreshold = 20;

{% endhighlight %}

### PullingThreshold

The [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) property indicates the maximum pullable position of the progress view, to reach 100 % of pulling progress. Refreshing will be started in the view only when the pulling progress reaches 100 % and the touch is released. If the touch is released before the refresh  content reaches 100 % of pulling progress, pulling will be canceled and hence refreshing will not occur.

Refer the below code example to set the [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) property.

{% highlight c# %}

pullToRefresh.PullingThreshold = 125;

{% endhighlight %}

The default value of [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) is 120.

N> [SfPullToRefresh.RefreshContentThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentThreshold.html) and [SfPullToRefresh.PullingThreshold](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~PullingThreshold.html) should have a difference of at least 100. Only then the animations of the pullable content will be visible in `TransitionType.Push` mode of animation.

### RefreshContentRadius

The radius of the progress view can be customized using [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) property. The default value of [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) is 25. 
Refer the below code example to set the [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~RefreshContentRadius.html) property

{% highlight c# %}

pullToRefresh.RefreshContentRadius = 20;

{% endhighlight %}

### ProgressStrokeWidth

The width of the inner stroke of the progress view can be customized using the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeWidth.html) property. The default width of the inner stroke of the progress view is "3".

Refer the below code example to set the [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeWidth.html) property.

{% highlight c# %}

pullToRefresh.ProgressStrokeWidth = 2;

{% endhighlight %}

### ProgressStrokeColor

The color of the inner stroke of the progress view is customizable. The default color of the inner stroke of the progress view is "Blue".

Refer the below code example to set the [SfPullToRefresh.ProgressStrokeColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressStrokeColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressStrokeColor = Android.Graphics.Color.Black;

{% endhighlight %}

### ProgressBackgroundColor

The background color of the progress view can be changed as per the requirement. The default background color of the progress view is "White".

Refer the below code example to set the [SfPullToRefresh.ProgressBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressBackgroundColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressBackgroundColor = Android.Graphics.Color.Yellow;

{% endhighlight %}

### ProgressShadowColor

The shadow color of the progress view can be customized using [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressShadowColor.html) property. The default background color of the progress view is "Android.Graphics.Color.Rgb(242, 242, 242)". 

In cases, where the background color of the pullable content and the progress view are same, use the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressShadowColor.html) to separate the progress view view from the pullable content view, which enhances the visual appearance of the application. 

Refer the below code example to set the [SfPullToRefresh.ProgressShadowColor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~ProgressShadowColor.html) property.

{% highlight c# %}

pullToRefresh.ProgressShadowColor = Android.Graphics.Color.LightYellow;

{% endhighlight %}

### Progress

The progress of pulling can be tracked using [SfPullToRefresh.Progress](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Progress.html) property. The progress of pulling is also provided in the [PullingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.PullingEventArgs.html) of the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Pulling_EV.html) event. Refer the topic [Pulling Event](#pulling-event) for more details regarding it.

### IsRefreshing

The [SfPullToRefresh.IsRefreshing](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~IsRefreshing.html) flag returns a value indicating whether refreshing is being done or not. When the refreshing is started in the SfPullToRefresh, it returns true and once the refreshing is completed, it resets to false.

## Events in SfPullToRefresh

There are three built-in events in SfPullToRefresh, which are listed below:

* [Pulling Event](#pulling-event)
* [Refreshing Event](#refreshing-event)
* [Refreshed Event](#refreshed-event)

### Pulling Event

The pulling event will be fired continuously as long as the pulling action is performed in the SfPullToRefresh. The progress of pulling can be tracked by the [PullingEventArgs.Progress](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.PullingEventArgs~Progress.html) property.

Refer the below code example illustrating hooking of the [SfPullToRefresh.Pulling](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Pulling_EV.html) event. 

{% highlight c# %}

pullToRefresh.Pulling += PullToRefresh_Pulling;

private void PullToRefresh_Pulling(object sender, PullingEventArgs e)
{
    progressOfPulling = e.Progress;
}

{% endhighlight %}

### Refreshing Event

To refresh the view, the user should hook the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event. The [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event will be fired, once the pulling progress reaches 100% and the touch is released. The user can do the required operations to refresh the view and once the view is refreshed, set the [RefreshingEventArgs.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.RefreshingEventArgs~Refreshed.html) as <b>true</b> to stop the refreshing animation. 

Refer the below code example illustrating hooking of the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshing_EV.html) event and refreshing the view.

{% highlight c# %}

public class MainActivity : Activity 
{
    ImageView weatherImage;
    TextView weatherData;
    Random random;
    string[] temperatures = new string[] { "22.01°", "23.11°", "22.50°", "22.77°", "22.20°", "22.00°", "24.01°" };
    int[] weatherImages = new int[] { Resource.Drawable.Cloudy, Resource.Drawable.Humid, Resource.Drawable.Rainy, Resource.Drawable.Warm, Resource.Drawable.Windy };

    protected override void OnCreate(Bundle bundle)
    {
	    ....
	    weatherImage = linearLayout.FindViewById<ImageView>(Resource.Id.weatherImage);
        weatherData = linearLayout.FindViewById<TextView>(Resource.Id.weatherData);
	    //Hooking the Refreshing event.
	    pullToRefresh.Refreshing += PullToRefresh_Refreshing;
	    random = new Random();
	    ....
    }

    private async void PullToRefresh_Refreshing(object sender, RefreshingEventArgs e)
    {
        await Task.Delay(3000);
        weatherImage.SetImageResource(weatherImages[random.Next(0, 4)]);
        weatherData.Text = temperatures[random.Next(1, 5)].ToString() + " degrees";
	    //Setting the e.Refreshed = true, to indicate that the view is refreshed and the SfPullToRefresh can stop the refreshing animation.
        e.Refreshed = true;
    }
}

{% endhighlight %}

### Refreshed Event

The [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshed_EV.html) event will be fired once the refreshing animation is completed, to indicate that the view is refreshed. 

Refer the below code example illustrating hooking of the [SfPullToRefresh.Refreshed](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~Refreshed_EV.html) event.

{% highlight c# %}

pullToRefresh.Refreshed += PullToRefresh_Refreshed;

private void PullToRefresh_Refreshed(object sender, EventArgs e)
{
    //Event will be fired once the refreshing is completed, the user can do the needful here.
}

{% endhighlight %}

## Programmatic Refresh

SfPullToRefresh supports refreshing the pullable content programmatically, without interaction. To refresh, the pullable content programmatically call the [SfPullToRefresh.StartRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~StartRefreshing.html) method and to end the programmatic refresh, call the [SfPullToRefresh.EndRefreshing()](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpulltorefresh/Syncfusion.SfPullToRefresh.Android~Syncfusion.SfPullToRefresh.SfPullToRefresh~EndRefreshing.html) method.

Refer the below code example to refresh the pullable content programmatically.

{% highlight c# %}

private async void PerformRefreshing()
{
    //Starts the refreshing.
    pullToRefresh.StartRefreshing();
    await Task.Delay(3000);
    weatherImage.SetImageResource(weatherImages[random.Next(0, 4)]);
    weatherData.Text = temperatures[random.Next(1, 5)].ToString() + "degrees";
    //Ends the refreshing.
    pullToRefresh.EndRefreshing();
}

{% endhighlight %}

The below GIF demonstrates the programmatic refresh:

<div style="text-align:center" markdown="1">
![](built_in_customization_images\ProgrammaticRefresh_Android.gif)
</div>
