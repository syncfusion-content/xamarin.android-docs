---
layout: post
title: Getting Started with Syncfusion® NumericUpDown for Xamarin.Android
description: A quick tour for initial users on the Syncfusion® NumericUpDown (SfNumericUpDown) control for the Xamarin.Android platform.
platform: xamarin.android
control: NumericUpDown 
documentation: ug
keywords: NumericUpDown, SfNumericUpDown, getting started, Xamarin.Android, setup, installation
---

# Getting Started with Xamarin.Android NumericUpDown (SfNumericUpDown)

This section provides an overview for working with the Essential<sup>®</sup> NumericUpDown control for Xamarin.Android. You can walk through the entire process of creating and configuring an `SfNumericUpDown` control.

## Reference Essential Studio<sup>®</sup> Components in Your Solution

After installing Essential Studio<sup>®</sup> for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfNumericUpDown.Android.dll

## Add SfNumericUpDown

The `SfNumericUpDown` control can be configured entirely in C# code or using AXML markup. The following steps explain how to create an `SfNumericUpDown` control and configure its elements.

### Using AXML Markup
Add the following code in the Main.axml file to include the `NumericUpDown` control:

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	android:orientation="vertical"
	android:layout_width="match_parent"
	android:layout_height="match_parent">

        <com.syncfusion.numericupdown.SfNumericUpDown 
	android:id="@+id/sfNumericUpDown"    
	android:layout_height="wrap_content" 
	android:layout_width="fill_parent" />

</LinearLayout> 
  
{% endhighlight %}

In MainActivity, you can access the `NumericUpDown` instance defined in the AXML page using the following code:

{% highlight C# %}

using Com.Syncfusion.NumericUpDown;

..

public class MainActivity : Activity
{
    protected override void OnCreate(Bundle savedInstanceState)
    {
    
        base.OnCreate(savedInstanceState);

        SetContentView(Resource.Layout.content_main);

        SfNumericUpDown numericUpDown = (SfNumericUpDown)FindViewById(Resource.Id.sfNumericUpDown);

        numericUpDown.Value = 30;
    }
}

{% endhighlight %}

Also, you can create the `NumericUpDown` control using the code behind. The following steps help to add the `NumericUpDown` control using the code behind.

* Adding reference to NumericUpDown.

{% capture codesnippet1 %}

{% tabs %}

{% highlight c# %}

using Com.Syncfusion.NumericUpDown;

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

* Create an instance of SfNumericUpDown.

{% capture codesnippet2 %}

{% tabs %}

{% highlight c# %}

SfNumericUpDown numeric = new SfNumericUpDown(this);
SetContentView(numeric);

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

## Set Value

The `SfNumericUpDown` control's display value can be set using the `Value` property:

{% tabs %}

{% highlight C# %}

numeric.Value= 5;

{% endhighlight %}

{% endtabs %}

## Enable Parsing Mode

The value of the `SfNumericUpDown` can be parsed based on the `ParsingMode` property, which determines how the input text is converted to a numeric value.

N> The `ParsingMode` is of type `Parsers` containing enum values of `Double` and `Decimal`.

{% tabs %}

{% highlight c# %}

	numeric.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

{% endtabs %}

## Add Format String

The `FormatString` property determines the format specifier by which the display text is formatted.

The control supports the following format types:
* **c** - Display the value with currency notation
* **n** - Display the value in number format
* **p** - Display the value in percentage format

N> The control displays the formatted text when it loses focus. The default value of `FormatString` is "n".

{% tabs %}

{% highlight C# %}

numeric.FormatString= “c”;

{% endhighlight %}

{% endtabs %}

![Xamarin.Android NumericUpDown getting started Image](images/gettingstarted.png)
