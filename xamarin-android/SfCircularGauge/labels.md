---

layout: post
title: Labels in Syncfusion SfCircularGauge control for Xamarin.Android 
description: Learn how to set labels and customize the labels in Syncfusion CircularGauge control for Xamarin.Android 
platform: Xamarin.Android
control: SfCircularGauge
documentation: ug

---

# Labels in SfCircularGauge

The [`CircularScale`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale.html) labels associate a numeric value with major scale tick marks.

## Label color customization

The label color can be changed using the [`LabelColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelColor.html) property.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelColor = Color.Blue;
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Label-color-customization image](labels_images/label-color-customization.png)

## Label font customization

The label font can be customized by using the [`LabelTextSize`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelTextSize.html), [`LabelTextStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelTextStyle.html) properties. 

{% highlight c# %}

           SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelTextStyle = Typeface.Create("calibri", TypefaceStyle.Italic);
            scale.LabelTextSize = 20;
            scales.Add(scale);
            circularGauge.CircularScales = scales; 
    
{% endhighlight %}

![Label-font-customization image](labels_images/label-font-customization.png)

## Setting position for labels

The labels can be positioned far away from the ticks by using the [`LabelOffset`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelOffset.html) property.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelOffset = 0.4;
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Label-offset image](labels_images/label-offset.png)

## Setting number of decimal digits for labels

The [`NumberOfDecimalDigits`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~NumberOfDecimalDigits.html) property is used to set the number of decimal digits to be displayed in the scale labels.

{% highlight c# %}

           SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.NumberOfDecimalDigits = 3;
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Number-of-decimal-digits image](labels_images/number-of-decimal-digits.png)

## Setting postfix and prefix for labels

You can postfix/prefix values to the scale labels by using the [`LabelPostfix`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelPostfix.html) and [`LabelPrefix`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~LabelPrefix.html) properties, respectively.

### Label postfix

`LabelPostfix` property allows you to postfix the values to the scale labels.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelPostfix = "$";
            scales.Add(scale);
            circularGauge.CircularScales = scales; 
    
{% endhighlight %}

![Label-postfix image](labels_images/label-postfix.png)

### Label prefix

`LabelPrefix` property allows you to prefix the values to the scale labels.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.LabelPrefix = "$";
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Label-prefix image](labels_images/label-prefix.png)

## Edge label customization

You can customize the edge label by using the [`ShowFirstLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~ShowFirstLabel.html) and [`ShowLastLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~ShowLastLabel.html) properties, which are Boolean properties. The [`ShowFirstLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~ShowFirstLabel.html) property is used to enable or disable first label, and the [`ShowLastLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~ShowLastLabel.html) property is used to enable or disable the last label in circular gauge.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.Interval = 1;
            scale.MinorTicksPerInterval = 5;
            scale.EndValue = 12;
            scale.StartAngle = 270;
            scale.SweepAngle = 360;
            scale.ShowFirstLabel = false;
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Label-edge-customization image](labels_images/label-edge-customization.png)

## Show labels

The [`ShowLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~ShowLabels.html) property is a Boolean property, which is used to enable or disable the labels in circular gauge.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.ShowLabels = false;
            scales.Add(scale);
            circularGauge.CircularScales = scales;
    
{% endhighlight %}

![Show-labels image](labels_images/show-labels.png)

## Setting auto angle for label

Scale labels can be rotated automatically based on the current angle. To enable or disable the auto angle, use the [`EnableAutoAngle`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfGauge.Android~Com.Syncfusion.Gauges.SfCircularGauge.CircularScale~EnableAutoAngle.html) property.

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge(this);
            ObservableCollection<CircularScale> scales = new ObservableCollection<CircularScale>();
            CircularScale scale = new CircularScale();
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.EnableAutoAngle = true;
            scales.Add(scale);
            circularGauge.CircularScales = scales;  
    
{% endhighlight %}

![Auto angle image](labels_images/auto-angle.png)

