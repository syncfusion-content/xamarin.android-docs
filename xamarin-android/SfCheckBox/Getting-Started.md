---
layout: post
title: Getting Started with Syncfusion® CheckBox for Xamarin.Android Platform
description: Learn how to create a simple CheckBox and their customization options with the available basic features in Xamarin.Android
platform: xamarin.android
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Getting Started with Xamarin.Android CheckBox (SfCheckBox)
This section explains the steps required to configure the [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) control in a real-time scenario and provides a walk-through on some of the customization features available in the [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) control.

## Add SfCheckBox Reference
Syncfusion<sup>®</sup> Xamarin components are available in [nuget.org](https://www.nuget.org/). To add CheckBox to your project, open the NuGet package manager in Visual Studio, search for "[Syncfusion.Xamarin.Buttons.Android](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons.Android)", and then install it.

![Xamarin.Android CheckBox NuGet](Images/nuget.png)

N> Starting with v16.2.0.x, if you reference Syncfusion<sup>®</sup> assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion<sup>®</sup> license key in your Xamarin application to use our components.

## Create a Simple SfCheckBox
The [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) control is configured entirely in C# code. The following steps explain how to create a [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) and configure its elements.

### Add Namespace for Referenced Assemblies

{% tabs %}
{% highlight c# %}
using Syncfusion.XForms.Buttons;
{% endhighlight %}
{% endtabs %}

### Refer SfCheckBox Control with Declared Suffix Name for Namespace

{% tabs %}
{% highlight c# %}
using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.Android.Buttons;

namespace SfCheckBox_Sample
{
    [Activity(Label = "SfCheckBox_Sample", MainLauncher = true, Icon = "@mipmap/icon")]
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);
            SetContentView(Resource.Layout.Main);
            LinearLayout linearLayout = FindViewById<LinearLayout>(Resource.Id.layout);
            SfCheckBox checkBox = new SfCheckBox(this);            
            linearLayout.AddView(checkBox);
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Setting Caption
The CheckBox caption can be defined using the `Text` property of [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html). This caption normally describes the meaning of the CheckBox and displays next to the CheckBox.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox(this);
checkBox.Checked = true;
checkBox.Text = "CheckBox";
{% endhighlight %}
{% endtabs %}

![Xamarin.Android CheckBox caption](Images/Caption.png) 

## Change the CheckBox State

The three visual states of [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) are: 

* Checked
* Unchecked
* Indeterminate

![Xamarin.Android CheckBox states](Images/States.png) 

You can change the state of the CheckBox using the [`Checked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_Checked) property of [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html). In the checked state, a tick mark is added to the visualization of the CheckBox.

<table>
<tr>
<td>
<b>State</b>
</td>
<td>
<b>Property</b>
</td>
<td>
<b>Value</b>
</td>
</tr>
<tr>
<td>
Checked
</td>
<td>
Checked
</td>
<td>
true
</td>
</tr>
<tr>
<td>
Unchecked
</td>
<td>
Checked
</td>
<td>
false
</td>
</tr>
<tr>
<td>
Indeterminate
</td>
<td>
Checked
</td>
<td>
null
</td>
</tr>
</table>

N> For the CheckBox to report the indeterminate state, set the [`IsThreeState`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_IsThreeState) property to `true`.

CheckBox can be used as a single control or as a group. A single CheckBox is mostly used for a binary yes/no choice, such as "Remember me?", login scenario, or a terms of service agreement.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox(this);
checkBox.Text = "I agree to the terms of services for this site";
checkBox.Checked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.Android CheckBox tri-state](Images/Agree.png)

Multiple CheckBoxes can be used as a group for multi-select scenarios in which a user chooses one or more items from the group of choices that are not mutually exclusive.

{% tabs %}
{% highlight c# %}
TextView label = new TextView(this);
label.Text = "Pizza Toppings";
SfCheckBox pepperoni = new SfCheckBox(this);
pepperoni.Text = "Pepperoni";
SfCheckBox beef = new SfCheckBox(this);
beef.Text = "Beef";
beef.Checked = true;
SfCheckBox mushroom = new SfCheckBox(this);
mushroom.Text = "Mushrooms";
SfCheckBox onion = new SfCheckBox(this);
onion.Text = "Pepperoni";
onion.Checked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.Android CheckBox multi-selection](Images/StateChange.png)

## Indeterminate

The [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) allows an indeterminate state in addition to the checked and unchecked states. The indeterminate state of the CheckBox is enabled by setting the [`IsThreeState`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_IsThreeState) property of the control to `true`.

N> When the [`IsThreeState`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_IsThreeState) property is set to `false` and [`Checked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_Checked) property is set to `null`, then the CheckBox will be in unchecked state.

The indeterminate state is used when a group of sub-choices has both checked and unchecked states. In the following example, the "Select all" CheckBox has the [`IsThreeState`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_IsThreeState) property set to `true`. The "Select all" CheckBox is checked if all child elements are checked, unchecked if all the child elements are unchecked, and indeterminate otherwise.

{% tabs %}
{% highlight c# %}
bool skip = false;
SfCheckBox selectAll, pepperoni, beef, mushroom, onion;
selectAll = new SfCheckBox(this);
selectAll.StateChanged += SelectAll_StateChanged;
selectAll.Text = "Select All";
pepperoni = new SfCheckBox(this);
pepperoni.StateChanged += CheckBox_StateChanged;
pepperoni.Text = "Pepperoni";
beef = new SfCheckBox(this);
beef.StateChanged += CheckBox_StateChanged;
beef.Text = "Beef";
beef.Checked = true;
mushroom = new SfCheckBox(this);
mushroom.StateChanged += CheckBox_StateChanged;
mushroom.Text = "Mushrooms";
onion = new SfCheckBox(this);
onion.StateChanged += CheckBox_StateChanged;
onion.Text = "Onions";
onion.Checked = true;

private void SelectAll_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       pepperoni.Checked = beef.Checked = mushroom.Checked = onion.Checked = e.IsChecked;
       skip = false;
    }
}

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       if (pepperoni.Checked.Value && beef.Checked.Value && mushroom.Checked.Value && onion.Checked.Value)
           selectAll.Checked = true;
        else if (!pepperoni.Checked.Value && !beef.Checked.Value && !mushroom.Checked.Value && !onion.Checked.Value)
	       selectAll.Checked = false;
       else
           selectAll.Checked = null;
       skip = false;
    }
}
		
{% endhighlight %}
{% endtabs %}

![Xamarin.Android CheckBox intermediate state](Images/Inter1.jpg) ![Xamarin.Android CheckBox intermediate state](Images/Inter2.jpg)

N> This demo can be downloaded from this [link](https://github.com/SyncfusionExamples/GettingStarted-Sample-in--CheckBox-Android).
