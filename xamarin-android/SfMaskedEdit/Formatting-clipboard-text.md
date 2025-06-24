---
layout: post
title: Formatting Clipboard Text of SfMaskedEdit in Xamarin.Android Platform
description: Learn how to format the clipboard text during cut and copy operations of the SfMaskedEdit control.
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit, clipboard, cut, copy, formatting

---

# Formatting Clipboard Text

The `SfMaskedEdit` control allows you to format clipboard text in mask scenarios (when the `Mask` property is set). When you perform cut or copy operations, the clipboard text is formatted with your input characters and the literals defined in the mask. You can modify this behavior and control whether the clipboard holds characters with or without prompt characters and literals by setting the `CutCopyMaskFormat` property of the control.

The clipboard text can be formatted using any of the following `MaskFormat` enumeration values:
* `ExcludePromptAndLiterals`
* `IncludePrompt`
* `IncludeLiterals`
* `IncludePromptAndLiterals`

## ExcludePromptAndLiterals

The clipboard text will contain only the typed characters. Prompt characters and literals are excluded.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.ExcludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePrompt

The clipboard text contains the typed characters and prompt characters. Literals are excluded.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePrompt;
{% endhighlight %}
{% endtabs %}

## IncludeLiterals

The clipboard text contains the typed characters and literals. Prompt characters are excluded.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludeLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePromptAndLiterals

The clipboard text contains typed characters, prompt characters, and literals.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}

