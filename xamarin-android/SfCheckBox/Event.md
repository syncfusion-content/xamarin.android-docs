---
layout: post
title: Event in SfCheckBox for Xamarin.Android platform
description: Learn how to customize the basic  Event in StateChanged event of SfCheckBox Xamarin.Android Platform 
platform: Xamarin.Android
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event in Xamarin.Android Chart(SfChart)

## StateChanged event
Occurs when the value(state) of the [`Checked`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfCheckBox~Checked.html) property is changed by either touching the check box or setting the value to the [`Checked`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfCheckBox~Checked.html) property using C# code. The event arguments are of type [`StateChangedEventArgs`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.StateChangedEventArgs.html) and expose the following property:

* [`IsChecked`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.StateChangedEventArgs~IsChecked.html): The new value(state) of the [`Checked`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.Buttons.Android~Syncfusion.Android.Buttons.SfCheckBox~Checked.html) property.

{% tabs %}
{% highlight c# %}
checkBox = new SfCheckBox(this);
checkBox.Text = "Unchecked State";
checkBox.IsThreeState = true;
checkBox.StateChanged += CheckBox_StateChanged;

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        checkBox.Text = "Checked State";
    }
    else if(e.IsChecked.HasValue && !e.IsChecked.Value)
    {
        checkBox.Text = "Unchecked State";
    }
    else
    {
        checkBox.Text = "Indeterminate State";
    }
}
		
{% endhighlight %}
{% endtabs %}

![](Images/Event1.png)
![](Images/Event2.png)
![](Images/Event3.png)
