---
layout: post
title: Data source  in Syncfusion Segmented control for Xamarin.Android
description: Learn how to add data sources with collection of strings, segment items, and custom views for Segmented control in Xamarin.Android
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Populating data source

The segmented control can be populated from a collection of strings, views, or a collection of objects in a built-in class.

## String collection

The segmented control provides the collection of strings as a data source.

{% highlight c# %}

[C#]

...

SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
segmentedControl.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 300);
segmentedControl.SelectionTextColor = Color.ParseColor("#02A0AE");
segmentedControl.BackColor = Color.Transparent;
segmentedControl.BorderColor = Color.ParseColor("#3F3F3F");
segmentedControl.FontColor = Color.Black;
segmentedControl.SelectedIndex = 2;
segmentedControl.BorderThickness = 15;
segmentedControl.FontSize = 15;
segmentedControl.SegmentPadding = 25;
segmentedControl.SegmentBackgroundColor = Color.Transparent;
segmentedControl.VisibleSegmentsCount = 3;
segmentedControl.DisplayMode = SegmentDisplayMode.Text;
segmentedControl.ItemsSource = new List<String>
{
    "Formals","Casuals","Trendy"
};

...

{% endhighlight %}

![Xamarin.Android SfSegmentedControl populating items with string items](images/Data-source/Xamarin_Android_string.png)

## Segment items

The segmented control customize the text or icons, or use other built-in customization options available for the segments. Segment item collections can also be used.

{% highlight c# %}

[C#]

...
SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
segmentedControl.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 400);
segmentedControl.SelectionTextColor = Color.ParseColor("#007CEE");
segmentedControl.VisibleSegmentsCount = 5;
segmentedControl.BackColor = Color.White;
segmentedControl.BorderColor = Color.ParseColor("#929292");
segmentedControl.SelectedIndex = 0;
segmentedControl.FontColor = Color.Black;
segmentedControl.SegmentBackgroundColor = Color.Transparent;
segmentedControl.ItemsSource = new ObservableCollection<SfSegmentItem>
{
    new SfSegmentItem(){Text="XS",FontColor=Color.ParseColor("#3F3F3F")}, 
    new SfSegmentItem(){Text="S",FontColor=Color.ParseColor("#3F3F3F")},
    new SfSegmentItem(){Text="M",FontColor=Color.ParseColor("#3F3F3F")},
    new SfSegmentItem(){Text="L",FontColor=Color.ParseColor("#3F3F3F")},
    new SfSegmentItem(){Text="XL",FontColor=Color.ParseColor("#3F3F3F")},
};

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Color = Color.White
};

...

{% endhighlight %}

![Xamarin.Android SfSegmentedControl populating items with segment items](images/Data-source/Xamarin_Android_SegmentItemCollection.png) 
   
## Custom views

Custom views or images can be added as segments in the Segmented control.

{% highlight c# %}

[C#]

...
SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
segmentedControl.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 100);
segmentedControl.BorderColor = Color.Transparent;
segmentedControl.SegmentHeight = 100;
segmentedControl.VisibleSegmentsCount = 2;
segmentedControl.BackColor = Color.Transparent;
segmentedControl.SegmentPadding = 30;
Button resetButtonView = new Button(this) { Text = "Reset", TextAlignment = TextAlignment.Center};
resetButtonView.SetHeight(50);
resetButtonView.SetBackgroundColor(Color.White);
resetButtonView.SetTextColor(Color.Gray);

Button goButtonView = new Button(this) { Text = "Go", TextAlignment = TextAlignment.Center};
goButtonView.SetHeight(50);
goButtonView.SetTextColor(Color.Gray);
goButtonView.SetBackgroundColor(Color.White);

segmentedControl.ItemsSource = new ObservableCollection<View>
{
    ResetButtonView,
    GoButtonView
};

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{ 
    Color = Color.Transparent,
    Position = SelectionIndicatorPosition.Fill,
    StrokeThickness = 10
};

...
{% endhighlight %}

![Xamarin.Android SfSegmentedControl populating items with custom views](images/Data-source/Xamarin_Android_Itemcolor.png)


