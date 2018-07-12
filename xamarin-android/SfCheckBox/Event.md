---
layout: post
title: Event in SfCheckBox for Xamarin.Android platform
description: Learn how to customize the basic features of SfCheckBox
platform: Xamarin.Android
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event

## StateChanged event
Occurs when the value(state) of the `Checked` property is changed by either touching the check box or setting the value to the `Checked` property using C# code. The event arguments are of type `StateChangedEventArgs` and expose the following property:

* `IsChecked`: The new value(state) of the `Checked` property.

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

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/CheckBox_Event.zip ).