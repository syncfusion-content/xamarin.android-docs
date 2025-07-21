---
layout: post
title: Basic Features in Syncfusion® MaskedEdit for Xamarin.Android Platform
description: Learn how to customize the value and configure prompt characters and hint text for the Syncfusion® MaskedEdit control.
platform: xamarin.android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit, prompt character, hint text, value setting
---

# Basic Features in MaskedEdit


## Setting Value

The `SfMaskedEdit` control displays a value that can be configured using the `Value` property:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.Mask = "00/00/0000";
maskedEdit.Value =@"14/11/2014";
{% endhighlight %}
{% endtabs %}

![Setting value](SfMaskedEditImages/BF_SetValue.png)


## Setting Prompt Character

The prompt character is displayed when no input is provided for a mask position. The default value is '_'. You can customize the prompt character using the `PromptChar` property:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.Mask = "00/00/0000";
maskedEdit.PromptChar = '*';
{% endhighlight %}
{% endtabs %}

![Prompt Character](SfMaskedEditImages/BF_Prompt.png)

## Setting Hint Text

The hint text provides instructions or important information when the control is not focused and no valid characters have been entered. Use the `Hint` property of `SfMaskedEdit` to configure the hint text for the control.

The following properties are available to customize the hint text appearance:

* `SetHintTextColor`: Sets the text color for the hint
* `HintTypeface`: Sets the font family and font attributes (bold/italic/normal) for the hint
* `HintTextSize`: Sets the font size for the hint

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.Mask = "00/00/0000";
maskedEdit.Hint = "Type here";
maskedEdit.SetHintTextColor(Color.LightGray);
maskedEdit.HintTypeface = Typeface.Create("Arial", TypefaceStyle.Bold);
maskedEdit.HintTextSize = 20;
{% endhighlight %}
{% endtabs %}

![Setting Hint](SfMaskedEditImages/BF_Hint.png)

You can find the complete basic features sample from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_BasicFeatures.zip).