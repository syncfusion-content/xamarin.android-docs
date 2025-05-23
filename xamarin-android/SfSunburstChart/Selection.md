---
layout: post
title: Selection feature of Essential<sup>&reg;</sup> Xamarin.Android SfSunburstChart
description: This section describes the segment selection.
platform: Xamarin.Android
control: SfSunburstChart
documentation: ug
---

# Selection

The sunburst chart provides support to select or highlight the segments. Selection can be enabled with the help of [`EnableSelection`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_EnableSelection) property.

## Selection type

The [`SelectionType`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_SelectionType) property allows you to select a segment based on the following categories:

* Child: Highlights the selected segment along with its children in all levels.
* Group: Highlights the entire group of the selected segment in a hierarchy.
* Parent: Highlights the parent of the selected segment in the hierarchy.
* Single: Highlights the selected segment alone.

### Child

The following code shows the `Child` selection type.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.Opacity = 0.5;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Child;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Child.jpg)

### Group

The following code shows the `Group` selection type.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.Opacity = 0.5;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Group.jpg)

### Parent

The following code shows the `Parent` selection type.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.Opacity = 0.5;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Parent;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Parent.jpg)

### Single

The following code shows the `Single` selection type.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.Opacity = 0.5;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Single;

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Single.jpg)

## Selection display mode

The [`SelectionDisplayMode`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_SelectionDisplayMode) property provides the following selection options to highlight the segments:

* By stroke
* By Color
* By opacity

### Opacity

This mode highlights the selected segment with the opacity specified in the [`Opacity`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_Opacity) property.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.Opacity = 0.5;           
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;
  sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByOpacity;

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Group.jpg)

### Color

This mode highlights the selected segment using the brush specified in the [`SelectionBrush`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_SelectionBrush) property.

{% tabs %}

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;  
  sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByColor;          
  sunburstChart.SelectionSettings.SelectionBrush = Color.Black;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;          

{% endhighlight %}

{% endtabs %} 

![](Selection_images/ColorSelection.png)

### Stroke

This mode highlights the selected segment by applying stroke to it. The color and thickness of the stroke can be customized using the [`SelectionStrokeBrush`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_SelectionStrokeBrush) and [`SelectionStrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SelectionSettings.html#Syncfusion_SfSunburstChart_Android_SelectionSettings_SelectionStrokeWidth) properties.

{% tabs %}

{% highlight C# %} 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByStroke;           
  sunburstChart.SelectionSettings.SelectionBrush = Color.Black;
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;          

{% endhighlight %}

{% endtabs %} 

![](Selection_images/StrokeSelection.png)

## Events

### Selection Changed

This event occurs whenever you select the segment. You can get the [`SelectedSegment`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SunburstSelectionChangedEventArgs.html#Syncfusion_SfSunburstChart_Android_SunburstSelectionChangedEventArgs_SelectedSegment) and [`IsSelected`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SunburstSelectionChangedEventArgs.html#Syncfusion_SfSunburstChart_Android_SunburstSelectionChangedEventArgs_IsSelected) properties details as argument from [`SunburstSelectionChangedEventArgs`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SunburstSelectionChangedEventArgs.html) handler.

{% tabs %} 

{% highlight C# %}

  Toast toast = new Toast(this); 

  sunburstChart.SelectionSettings.EnableSelection = true;
  sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByStroke;  
  sunburstChart.SelectionSettings.SelectionType = SelectionType.Single;     

  sunburstChart.SelectionChanged += SunburstChart_SelectionChanged;   

  private void SunburstChart_SelectionChanged(object sender, SunburstSelectionChangedEventArgs e)
  {
     if (e.SelectedSegment != null)
     {
         if (toast != null)
            toast.Cancel();                

         if (e.SelectedSegment.CurrentLevel == 0)
         {
             toast = Toast.MakeText(this, "Country : " + e.SelectedSegment.Category + "\n" +
                  "Employees Count : " + e.SelectedSegment.Value, ToastLength.Short);
             toast.Show();                   
         }               
     }            
  }

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Event.png)
