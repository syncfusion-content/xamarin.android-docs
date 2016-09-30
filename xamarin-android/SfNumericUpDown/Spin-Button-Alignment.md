---
layout: post
title: Appearance in Syncfusion NumericUpDown control for Xamarin.Android
description: Learn how to add customize spin buttons position in NumericUpDown.
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

Spin Button position in the SfNumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

* Right
* Left
* Both

### Right

Spin Buttons will get aligned to the right side of the control.

{% tabs %}

{% highlight C# %}

numericupdown.SpinButttonAlignment = SpinButtonAlignment.Right;

{% endhighlight %}

{% endtabs %}

![](images/spinright.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight C# %}

numericupdown.SpinButttonAlignment = SpinButtonAlignment.Left;

{% endhighlight %}

{% endtabs %}

![](images/spinleft.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% tabs %}

{% highlight C# %}

numericupdown.SpinButttonAlignment = SpinButtonAlignment.Both;

{% endhighlight %}

{% endtabs %}

![](images/spinboth.png)

N> By default the property value is Right.



