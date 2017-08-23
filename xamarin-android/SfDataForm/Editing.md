---
layout: post
title: Editing | SfDataForm | Xamarin.Android | Syncfusion
description: Editing in SfDataForm
platform: xamarin.Android
control: SfDataForm
documentation: ug
---

# Editing 
SfDataForm provides support for several built-in editors. 

## Supported editors and associated DataFormItem

<table>
<tr>
<th>Editor name</th>
<th>Editor class</th>
<th>Data Type/Attribute</th>
<th>Input control loaded</td>
</tr>
<tr>
<td>
Text
</td>
<td>
{{'[DataFormTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html#"")'| markdownify }}
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
{{'[DataFormMultiLineTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormMultiLineTextEditor.html#"")'| markdownify }}
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
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html#"")'| markdownify }}
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
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html#"")'| markdownify }}
</td>
<td>
Property of type int, double, float, decimal, long types and its nullable also properties with below attributes. [DataType(“Percent”)].
</td>
<td>
SfNuemricTextBox
</td>
</tr>
<tr>
<td>
Currency
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html#"")'| markdownify }}
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
{{'[DataFormDateEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormDateEditor.html#"")'| markdownify }}
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
{{'[DataFormTimeEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTimeEditor.html#"")'| markdownify }}
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
{{'[DataFormNumericUpDownEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormNumericUpDownEditor.html#"")'| markdownify }}
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
{{'[DataFormSegmentedEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormSegmentedEditor.html#"")'| markdownify }}
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
{{'[DataFormCheckBoxEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormCheckBoxEditor.html#"")'| markdownify }}
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
{{'[DataFormSwitchEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormSwitchEditor.html#"")'| markdownify }}
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
{{'[DataFormPickerEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormPickerEditor.html#"")'| markdownify }}
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
{{'[DataFormDropDownEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormDropDownEditor.html#"")'| markdownify }}
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

## Changing editor for type

By default, editors will be loaded based on above table. If you want to change the editor for any type, you need to use [RegisterEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~RegisterEditor(Type,String).html) method and specify type and editor.

{% tabs %}
{% highlight c# %}

dataForm.RegisterEditor(typeof(int), "NumericUpDown");

{% endhighlight %}
{% endtabs %}

Here, `NumericUpDown` editor will be loaded for integer type instead of numeric editor.

## Changing editor for property

If you want to change the editor for any property, you need to use [RegisterEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~RegisterEditor(String,String).html) method and specify property name and editor.

{% tabs %}
{% highlight c# %}

dataForm.RegisterEditor("IsAvailable", "Switch");

{% endhighlight %}
{% endtabs %}

Here, Switch editor will be loaded for `IsAvailable` property (bool type) instead of `CheckBox` editor.

## Customizing existing editor

You can customize the existing editors defined in above table, by overriding default editors. 
Here,[DataFormTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html) is customized to set different foreground for FirstName property text editor.

{% tabs %}
{% highlight c# %}
public class CustomTextEditor : DataFormTextEditor
{
    public CustomTextEditor(SfDataForm dataForm) : base(dataForm)
    {
    }
    
    protected override void OnInitializeView(DataFormItem dataFormItem, EditText view)
    {
        if (dataFormItem.Name == "FirstName")
            view.SetTextColor(Color.Green);
        base.OnInitializeView(dataFormItem, view);
    }
}

dataForm.RegisterEditor("Text", new CustomTextEditor(dataForm));            
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/EditorCustomization.png)

## Creating new custom editor

You can create custom editor by overriding [DataFormEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormEditor%601.html) class.
Property settings, commit, data validation can be handled by overriding required methods. Here, `SeekBar` is loaded for `Salary` editor.

{% tabs %}
{% highlight c# %}
public class CustomSliderEditor : DataFormEditor<SeekBar>
{
    public CustomSliderEditor(SfDataForm dataform) : base(dataform)
    {
    }

    protected override SeekBar OnCreateEditorView()
    {
        return new SeekBar(this.dataForm.Context);
    }

    protected override void OnInitializeView(DataFormItem dataFormItem, SeekBar view)
    {
        view.Progress = (int)dataForm.ItemManager.GetValue(dataFormItem);
    }

    protected override void OnWireEvents(SeekBar view)
    {
        view.ProgressChanged += View_ProgressChanged;
    }
    protected override void OnUnWireEvents(SeekBar view)
    {
        view.ProgressChanged -= View_ProgressChanged;
    }
    private void View_ProgressChanged(object sender, SeekBar.ProgressChangedEventArgs e)
    {
        OnCommitValue(sender as SeekBar);
    }

    
    protected override void OnCommitValue(SeekBar view)
    {
        var dataFormItemView = view.Parent as DataFormItemView;
        dataForm.ItemManager.SetValue(dataFormItemView.DataFormItem, view.Progress);
    }
}

dataForm.RegisterEditor("Slider", new CustomSliderEditor(dataForm));
dataForm.RegisterEditor("Salary", "Slider");
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/SeekBarEditor.png)

## Support for password editor

You can load password editor by customizing [DataFormTextEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html) and setting `InputType` in ‘AutoGeneratingDataFormItem’ event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
        (e.DataFormItem as DataFormTextItem).InputType = Android.Text.InputTypes.ClassText | Android.Text.InputTypes.TextVariationPassword;
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/PasswordEditor.png)

## Support for Email editor

You can load Email editor by changing Input type in [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~AutoGeneratingDataFormItem_EV.html) event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem.Name == "Email")
        (e.DataFormItem as DataFormTextItem).InputType = Android.Text.InputTypes.TextVariationEmailAddress;
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/EmailEditor.png)

## Commit mode

[CommitMode](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.CommitMode.html) determines when the value should be committed to data object.

Below are the supported commit modes.

* LostFocus
* PropertyChanged
* Explicit

{% tabs %}
{% highlight c# %}
dataForm.CommitMode = CommitMode.LostFocus;
{% endhighlight %}
{% endtabs %}

**LostFocus**

If the commit mode is LostFocus, value is committed when the editor lost its focus.

**PropertyChanged**

Value is committed immediately when it is changed.

**Explicit**

Value should be committed manually by calling [SfDataForm.Commit](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~Commit().html) or [SfDataForm.Commit(propertyName)](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~Commit(String).html) method.

Below code commits the value of all the properties in data object.

{% tabs %}
{% highlight c# %}
dataForm.Commit();
{% endhighlight %}
{% endtabs %}

If you want to commit specific property value, you need to pass property name as argument.

{% tabs %}
{% highlight c# %}
dataForm.Commit("Name");
{% endhighlight %}
{% endtabs %}

## Update editor value based on another editor

You can the update the editor value by using [SfDataForm.UpdateEditor](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~UpdateEditor.html) method at runtime.

{% tabs %}
{% highlight c# %}
var expenseInfo = new ExpenseInfo();
expenseInfo.PropertyChanged += ExpenseInfo_PropertyChanged;
dataForm.DataObject = expenseInfo;
SetContentView(dataForm);

private void ExpenseInfo_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (e.PropertyName == "Budget" || e.PropertyName == "Expense")
    {
        var item = sender as ExpenseInfo;
        item.Balance = item.Budget - item.Expense;
        dataForm.UpdateEditor("Balance");               
    }
}
{% endhighlight %}
{% endtabs %}

Here, Balance property value is updated based on Budget and Expense properties. For updating value in editor, `UpdateEditor` method is called.

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/UpdateEditors1637679644).

## Converter

If you want to show the original value in different format or as different value, you need to use [Converter](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.ConverterAttribute.html) attribute.
Here, original value is multiplied by 10 and shown in editor. While committing, it is divided by 10 and stored in data object.

{% tabs %}
{% highlight c# %}
public class ValueConverterExt : IPropertyValueConverter
{
    public object Convert(object value)
    {            
        var amount = double.Parse(value.ToString());
        return amount * 10;
    }

    public object ConvertBack(object value)
    {
        var amount = double.Parse(value.ToString());
        return amount / 10;
    }
}

private double? amount = 1000;

[Converter(typeof(ValueConverterExt))]
public double? Amount
{
    get
    {
        return amount;
    }
    set
    {
        amount = value;
        RaisePropertyChanged("Amount");
    }
}
{% endhighlight %}
{% endtabs %}

## Disable editing

You can disable edit by setting [IsReadOnly](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~IsReadOnly.html) property of SfDataForm.

{% tabs %}
{% highlight c# %}
dataForm.IsReadOnly = true;
{% endhighlight %}
{% endtabs %}

You can also change the editing behavior by setting [IsReadOnly](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormItem~IsReadOnly.html) property of [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Salary")
            e.DataFormItem.IsReadOnly = true;
    }
}
{% endhighlight %}
{% endtabs %}

You can change the editing behavior at runtime also.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, System.EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["FirstName"];
    dataFormItem.IsReadOnly = true;
}
{% endhighlight %}
{% endtabs %}

N> [DataFormItem.IsReadOnly](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.DataFormItem~IsReadOnly.html) takes higher priority than [SfDataForm.IsReadOnly](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~IsReadOnly.html).

You can also have option to define the editing behavior from `SfDataForm.DataObject` definition using [ReadOnly](https://msdn.microsoft.com/en-us/library/system.componentmodel.readonlyattribute.aspx) attribute and [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx)


{% tabs %}
{% highlight c# %}
private double? balance;
[ReadOnly(true)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}
private double? balance;
[Editable(false)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}

{% endhighlight %}
{% endtabs %}

You can also define the editing behavior by defining [SfDataForm.DataObject](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfdataform/Syncfusion.SfDataForm.Android~Syncfusion.Android.DataForm.SfDataForm~DataObject.html) fields definition without `setter` or with `private set`.

{% tabs %}
{% highlight c# %}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }    
}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }
    private set
    {
        balance = value;
    }
}
{% endhighlight %}
{% endtabs %}
