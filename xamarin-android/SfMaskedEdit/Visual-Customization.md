---
layout: post
title: Visual Appearance Customization of SfMaskedEdit Control for Xamarin.Android Platform
description: Learn how to customize the visual appearance of the SfMaskedEdit control.
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit, visual customization, appearance, styling
---

# Visual Customization

The appearance of the `SfMaskedEdit` control can be customized using the following properties to match your application's design requirements.

The appearance of SfMaskedEdit can be customized using the following properties:

## BorderColor

Sets the custom border color to SfMaskedEdit.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.BorderColor = Color.Green;
{% endhighlight %}
{% endtabs %}

![Border Color Customization](SfMaskedEditImages/Visual_BorderColor.png)

### ErrorBorderColor

Sets a custom error border color for the `SfMaskedEdit` control. The error border color indicates the color to be used when validation fails for the input with respect to the mask pattern.

> **Note:** Validation triggers based on the `ValidationMode` property setting.

Refer to this [link](Validation#validation-mode) to learn more about the `ValidationMode` property of the `SfMaskedEdit` control.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ErrorBorderColor = Color.Yellow;
{% endhighlight %}
{% endtabs %}

![Error Border Color Customization](SfMaskedEditImages/Visual_ErrorBorderColor.png)

## Text Appearance Customization
 
You can customize the display text appearance of the `SfMaskedEdit` control using the following properties:

* `SetTextColor` - Changes the color of the text
* `TextAlignment` - Changes the horizontal alignment of the text
* `Typeface` - Changes the font family and sets font attributes (bold/italic/normal) of the text
* `TextSize` - Sets the font size of the text

### Example

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.SetTextColor(Color.Brown);
maskedEdit.TextAlignment = TextAlignment.Center;
maskedEdit.Typeface = Typeface.Create("Arial", TypefaceStyle.Bold);
maskedEdit.TextSize = 20;
{% endhighlight %}
{% endtabs %}

![Text Appearance Customization](SfMaskedEditImages/Visual_TextColor.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).
