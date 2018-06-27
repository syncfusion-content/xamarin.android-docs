---
layout: post
title: States
description: States.
platform: Xamarin.Android
control: ProgressBar
documentation: ug
---

# States

Based on the progress estimation, you can configure the states of the progress bar.

## Determinate

This is the default state. You can use it when the progress estimation is known.

## Indeterminate

By enabling the [`IsIndeterminate`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfprogressbar/Syncfusion.SfProgressBar.Android~Syncfusion.Android.ProgressBar.ProgressBarBase~IsIndeterminate.html) property, the state of the progress bar can be changed to indeterminate when progress cannot be estimated or is not being calculated. It can be combined with determinate mode to let users know that the app is estimating progress before actual progress starts.

{% highlight c# %}

            // Using linear progress bar. 
            LinearLayout linearLayout = new LinearLayout(this);
            linearLayout.LayoutParameters = new LinearLayout.LayoutParams(
                this.Resources.DisplayMetrics.WidthPixels - 120,
                this.Resources.DisplayMetrics.HeightPixels / 2);
            linearLayout.Orientation = Orientation.Vertical;
            SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar(this);
            sfLinearProgressBar.LayoutParameters = new LinearLayout.LayoutParams(
                this.Resources.DisplayMetrics.WidthPixels - 120,
                this.Resources.DisplayMetrics.HeightPixels / 18);
            sfLinearProgressBar.IsIndeterminate = true;
            linearLayout.AddView(sfLinearProgressBar);

            // Using circular progress bar.
            SfCircularProgressBar circularProgressBar = new SfCircularProgressBar(this);
            circularProgressBar.LayoutParameters = new LinearLayout.LayoutParams(
                this.Resources.DisplayMetrics.WidthPixels - 120,
                this.Resources.DisplayMetrics.HeightPixels / 2);
            circularProgressBar.IsIndeterminate = true;
            linearLayout.AddView(circularProgressBar);

            SetContentView(linearLayout);

{% endhighlight %} 

## Buffer

The secondary task’s progress can be defined by using the [`SecondaryProgress`](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfprogressbar/Syncfusion.SfProgressBar.Android~Syncfusion.Android.ProgressBar.SfLinearProgressBar~SecondaryProgress.html) property as shown in the following code example.

{% tabs %} 

{% highlight xaml %} 

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Progress="25" SecondaryProgress="75"/>

{% endhighlight %}

{% highlight c# %}

this.LinearProgressBar.Progress = 75;

this.LinearProgressBar.SecondaryProgress = 25;

{% endhighlight %}

{% endtabs %} 

![](overview_images/Buffer.png)
