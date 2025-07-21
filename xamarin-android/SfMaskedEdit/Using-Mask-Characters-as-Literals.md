---
layout: post
title: Using Mask Characters as Literals in Syncfusion® SfMaskedEdit
description: Learn how to use mask characters as literals in the SfMaskedEdit control for the Xamarin.Android platform.
platform: xamarin.android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit, literals, escape characters, backslash
---


# Using Mask Characters as Literals

To use a mask character as a literal, precede the mask character with a backslash (`\`). This escape sequence allows you to display special mask characters as static text rather than as input placeholders.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = @"\$ 0000";
{% endhighlight %}
{% endtabs %}

This mask will produce a display that shows a dollar sign (`$`) followed by prompt characters for entering four numeric digits.

![Using Mask Characters as Literals](SfMaskedEditImages/MaskAsLiterals.png)

You can download the complete mask characters as literals sample from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_UsingMaskCharactersAsLiterals.zip).
