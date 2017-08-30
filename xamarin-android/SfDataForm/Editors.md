---
layout: post
title: Layout | SfDataForm | Xamarin.Android | Syncfusion
description: Different editors and its customization  in SfDataForm.
platform: Xamarin.Android
control: SfDataForm
documentation: UG
---

# Editors

SfDataForm provides support for several built-in editors. Below are the supported editors.

<table>
<tr>
<th>Editor name</th>
<th>Editor class</th>
<th>Supported Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
</td>
<td>
{{'[DataFormTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html)'| markdownify }}
</td>
<td>
Property of type string and any other type apart from below specified cases.
</td>
<td>
EditText
</td>
</tr>
<tr>
<td>
MultilineText
</td>
<td>
{{'[DataFormMultiLineTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormMultiLineTextEditor.html)'| markdownify }}
</td>
<td>
Property of string type with Multiline text.
[DataType(DataType.Multiline)] 
</td>
<td>
EditText
</td>
</tr>
<tr>
<td>
Numeric
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes.
</td>
<td>
SfNumericTextBox
</td>
</tr>
<tr>
<td>
Percent
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes. [DataType(“Percent”)].
</td>
<td>
SfNumericTextBox
</td>
</tr>
<tr>
<td>
Currency
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes. [DataType(DataType.Currency)].
</td>
<td>
SfNumericTextBox
</td>
</tr>
<tr>
<td>
Date
</td>
<td>
{{'[DataFormDateEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormDateEditor.html)'| markdownify }}
</td>
<td>
Property of type DateTime and Property with below attribute
[DataType(DataType.Date)].
[DataType(DataType.DateTime)]
</td>
<td>
SfDatePicker
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
{{'[DataFormTimeEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTimeEditor.html)'| markdownify }}
</td>
<td>
Property with below attribute.
[DataType(DataType.Time)].
</td>
<td>
SfTimePicker
</td>
</tr>
<tr>
<td>
NumericUpDown
</td>
<td>
{{'[DataFormNumericUpDownEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericUpDownEditor.html)'| markdownify }}
</td>
<td>
Property of type Int or Double.
</td>
<td>
SfNumericUpDown
</td>
</tr>
<tr>
<td>
Segment
</td>
<td>
{{'[DataFormSegmentedEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormSegmentedEditor.html)'| markdownify }}
</td>
<td>
Property of type enum.
</td>
<td>
RadioGroup
</td>
</tr>
<tr>
<td>
Bool
</td>
<td>
{{'[DataFormCheckBoxEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormCheckBoxEditor.html)'| markdownify }}
</td>
<td>
Property of type bool
</td>
<td>
CheckBox
</td>
</tr>
<tr>
<td>
Switch
</td>
<td>
{{'[DataFormSwitchEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormSwitchEditor.html)'| markdownify }}
</td>
<td>
Property of type bool
</td>
<td>
Switch
</td>
</tr>
<tr>
<td>
Picker
</td>
<td>
{{'[DataFormPickerEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormPickerEditor.html)'| markdownify }}
</td>
<td>
Property of type enum and list. 
[EnumDataTypeAttribute]
</td>
<td>
SfPicker
</td>
</tr>
<tr>
<td>
DropDown
</td>
<td>
{{'[DataFormDropDownEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormDropDownEditor.html)'| markdownify }}
</td>
<td>
Property of type enum and list
[EnumDataTypeAttribute]
</td>
<td>
Spinner
</td>
</tr>
</table>

## Text Editor

In Text editor, [EditText](https://developer.xamarin.com/guides/android/user_interface/form_elements/edit_text/) is loaded.

### Loading upper case keyboard in EditText

You can load upper case letters keyboard by setting [InputType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormTextItem~InputType.html) as `TextFlagCapCharacters`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{    
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        (e.DataFormItem as DataFormTextItem).InputType = Android.Text.InputTypes.TextFlagCapCharacters;
    }
}
{% endhighlight %}
{% endtabs %}

## Numeric Editor

In numeric editor, [SfNumericTextBox](https://help.syncfusion.com/xamarin-android/introduction/overview) is loaded.

### Change maximum NumberDecimalDigits in Numeric editor

In `SfNumericTextBox`, two decimal digits will be displayed by default. You can change the number of decimal digits being displayed by setting [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericItemBase~MaximumNumberDecimalDigits.html) property in [DataFormNumericItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Amount")
    {
        (e.DataFormItem as DataFormNumericItem).MaximumNumberDecimalDigits = 3;
    }
}
{% endhighlight %}
{% endtabs %}

## Date Editor

In Date editor, [SfDatePicker](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.SfDatePicker.html) will be loaded.

### Customizing format in Date editor

In `SfDatePicker`, Short date will be shown by default. You can change the format to be applied by setting [Format](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDateItem~Format.html) property in [DataFormDateItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDateItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{   

    if (e.DataFormItem != null && e.DataFormItem.Name == "Date")
    {
        (e.DataFormItem as DataFormDateItem).Format = "ddd, MMM d, yyyy";
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/DateEditorFormat.png)

### Setting MaximumDate and MinimumDate in Date editor

You can customize the maximum and minimum allowable dates in `SfDatePicker` by setting [MaximumDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDateItem~MaximumDate.html) and [MinimumDate](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDateItem~MinimumDate.html) in [DataFormDateItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDateItem.html) respectively.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Date")
    {
        (e.DataFormItem as DataFormDateItem).MinimumDate = new DateTime(2017, 5, 5);
        (e.DataFormItem as DataFormDateItem).MaximumDate = new DateTime(2017, 9, 2);
    }
}

{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/DateEditorMax.png)

## Drop Down Editor

In drop down editor, [Spinner](https://developer.xamarin.com/guides/android/user_interface/spinner/) will be loaded.

### Customizing ItemsSource of spinner

By default, `ItemsSource` for spinner is auto-generated for enum types and collection type properties. For other types, you can set `ItemsSource` by using [SourceProvider](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~SourceProvider.html).

**Using SourceProvider**

{% tabs %}
{% highlight c# %}
private string _ItemName;
public string ItemName
{
    get
    {
        return _ItemName;
    }
    set
    {
        _ItemName = value;
    }
}
public class SourceProviderExt : SourceProvider
{
    public override IList GetSource(string sourceName)
    {
        var list = new List<string>();
        if (sourceName == "ItemName")
        {
            list.Add("Item1");
            list.Add("Item2");
            list.Add("Item3");
        }
        return list;
    }
}
dataForm.SourceProvider = new SourceProviderExt();
dataForm.RegisterEditor("ItemName", "DropDown");
{% endhighlight %}
{% endtabs %}

**Using ItemsSource property**

You can also set the ItemsSource for drop down editor by using [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormDropDownItem~ItemsSource.html) property in `DataFormDropDownItem`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (e.DataFormItem as DataFormDropDownItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/DropDownItems.png)

You can also change the `ItemsSource` at runtime.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["Name"];
    if (dataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (dataFormItem as DataFormDropDownItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

## Picker Editor

In picker editor, [SfPicker](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.SfPicker.html) will be loaded.

### Changing Title in SfPicker

You can show some text in `SfPicker` popup by using [Title](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormPickerItem~Title.html) property in [DataFormPickerItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormPickerItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        (e.DataFormItem as DataFormPickerItem).Title = "Expense Category";
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/PickerTitle.png)

### Customizing ItemsSource of SfPicker

By default, `ItemsSource` for picker is auto-generated for enum type and collection type properties. For other types, you can set `ItemsSource` by using [SourceProvider](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~SourceProvider.html).

**Using SourceProvider**

{% tabs %}
{% highlight c# %}
private string _ItemName;
public string ItemName
{
    get
    {
        return _ItemName;
    }
    set
    {
        _ItemName = value;
    }
}
public class SourceProviderExt : SourceProvider
{
    public override IList GetSource(string sourceName)
    {
        var list = new List<string>();
        if (sourceName == "ItemName")
        {
            list.Add("Item1");
            list.Add("Item2");
            list.Add("Item3");
        }
        return list;
    }
}
dataForm.SourceProvider = new SourceProviderExt();
dataForm.RegisterEditor("ItemName", "Picker");
{% endhighlight %}
{% endtabs %}

You can also set `ItemsSource` for picker editor by using [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormPickerItem~ItemsSource.html) property in [DataFormPickerItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormPickerItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (e.DataFormItem as DataFormPickerItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

You can also change the `ItemsSource` at runtime.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["Name"];
    if (dataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (dataFormItem as DataFormPickerItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

## NumericUpDown Editor

In numeric editor, [SfNumericUpDown](https://help.syncfusion.com/xamarin-android/sfnumericupdown/overview) will be loaded.

### Changing SpinButtonAlignment in NumericUpDown

By default, up down button will be displayed in right side. You can change its alignment by using [SpinButtonAlignment](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem~SpinButtonAlignment.html) property in [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
        (e.DataFormItem as DataFormNumericUpDownItem).SpinButtonAlignment = SpinButtonAlignment.Both;
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/SpinButtonCenter.png)

### Changing step value in NumericUpDown

You can change the next increment and decrement value by using [StepValue](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem~StepValue.html) property in [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html). The default value of step value is 1.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
        (e.DataFormItem as DataFormNumericUpDownItem).StepValue = 2;
}
{% endhighlight %}
{% endtabs %}

### Setting Maximum and Minimum value in NumericUpDown

You can set minimum and maximum value for numeric up down by using [Minimum](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem~Minimum.html) and [Maximum](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem~Maximum.html) property values respectively.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).Maximum = 100;
        (e.DataFormItem as DataFormNumericUpDownItem).Minimum = 0;
    }
}
{% endhighlight %}
{% endtabs %}

### Enabling Auto reverse in Numeric up down

In `SfNumericUpDown`, once maximum and minimum value reached, value will be unchanged. You can  enable cyclic behavior by setting [AutoReverse](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem~AutoReverse.html) as `true` in [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).AutoReverse = true;
    }
}
{% endhighlight %}
{% endtabs %}

### Changing CultureInfo in NumericUpDown and NumericTextBox

You can change the Culture in `SfNumericTextBox` and `SfNumericUpDown` by using [CultureInfo](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericItemBase~CultureInfo.html) property in [DataFormNumericItemBase](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormNumericItemBase.html).

**SfNumericTextBox**

{% tabs %}
{% highlight c# %}
private double _discount = 10;
        
[DataType(DataType.Currency)]
public double Discount
{
    get
    {
        return _discount;
    }
    set
    {
        _discount = value;
        RaisePropertyChanged("Discount");
    }
}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Discount")
    {
        (e.DataFormItem as DataFormNumericItem).CultureInfo = new Java.Util.Locale("fr", "FR");
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/NumericCulture.png)

**SfNumericUpDown**

{% tabs %}
{% highlight c# %}
dataForm.RegisterEditor("Discount", "NumericUpDown");
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Discount")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).FormatString = "c";
        (e.DataFormItem as DataFormNumericUpDownItem).CultureInfo = new Java.Util.Locale("fr", "FR");
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/NumericUpDownCulture.png)

