---
layout: post
title: Hiding Prompt Characters of SfMaskedEdit Control for Xamarin.Android Platform
description: Learn how to hide the prompt characters of the SfMaskedEdit control when the control loses focus.
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit, prompt characters, hide prompt, focus
---


# Hiding Prompt Characters

When the `HidePromptOnLeave` property is set to `true`, prompt characters are hidden when the control loses focus. The prompt characters are restored when the control regains focus.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.HidePromptOnLeave = true;
{% endhighlight %}
{% endtabs %}

![Hiding Prompt Characters](SfMaskedEditImages/HPL.png)

You can download the complete hiding prompt characters sample from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_HidingPrompt.zip).
