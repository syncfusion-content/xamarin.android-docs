# SfDataForm

SfDataForm control helps to edit data fields of any data object. It can be used to develop various forms such as login, reservation, data entry, and more. Key features include the following,

* Layout and Grouping - Support for linear and grid layout along with grouping support. Support to customize layout with different heights for each item.
* Caption Customization - Support to load images as captions for editor.
* Editors - Built-in support for text, numeric, numeric up-down, picker, date picker, time picker, switch and checkbox editors. 
* Custom Editor - Support for loading custom editors.
* Validation - Built-in support to validate data based on [IDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.idataerrorinfo.aspx# ""), [INotifyDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifydataerrorinfo.aspx# ""), and data annotations. And also, supports to handle validation programmatically.

# Getting Started

The section explains you the quick overview to use `SfDataFrom` for Xamarin.Android in your application.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,
{Syncfusion Essential Studio Installed location} \Essential Studio\15.x.x.x\Xamarin\lib
Eg: C:\Program Files (x86) \Syncfusion\Essential Studio\15.3.0.26\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.

The following list of assemblies need to be added as reference from the lib folder to use `SfDataForm` in your application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>
Xamarin.Android
</td>
<td>
Syncfusion.SfNumericUpDown.Android.dll<br/>Syncfusion.SfNumericTextBox.Android.dll<br/>Syncfusion.SfDataForm.Android.dll<br/></td>
</tr>
</table>

## Creating SfDataForm

In this section, you will create Xamarin.Android application with `SfDataForm`. The SfDataForm needs to be configured entirely in C# code
* Creating the project.
* Adding SfDataForm in Xamarin.Android.
* Creating DataObject.
* Setting DataObject.

### Creating the project

Create new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

### Adding SfDataForm in Xamarin.Android

To add SfDataForm to your application, do the following steps.

1. Add required assemblies as discussed in Assembly Deployment section.
2. Import the `SfDataForm` namespace `Syncfusion.Android.DataForm`.
3. Create instance of SfDataForm control and add as a view to a LinearLayout.

{% tabs %}
{% highlight c# %}

using Syncfusion.Android.DataForm;

[Activity(Label = "GettingStarted", MainLauncher = true, Icon = "@drawable/icon")]
public class MainActivity : Activity
{        
    protected override void OnCreate(Bundle bundle)
    {
        base.OnCreate(bundle);
            
        SetContentView(Resource.Layout.Main);
        var layOut = FindViewById<LinearLayout>(Resource.Id.linearLayout1);

        var dataForm = new SfDataForm(this);
        dataForm.DataObject = new ContactsInfo();

        layOut.AddView(dataForm);
    }
}

{% endhighlight %}
{% endtabs %}

### Creating DataObject

`SfDataForm` is a data edit control. So, you need to create the data object that you want to get edit.
Here data object named **ContactsInfo** created with properties.

{% tabs %}
{% highlight c# %}

public class ContactsInfo
{
    private string firstName;
    private string middelName;
    private string lastname;
    private string contactNo;
    private string email;
    private string address;
    private DateTime? birthDate;
    private string groupName;

    public ContactsInfo()
    {

    }

    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    public string MiddleName
    {
        get { return this.middelName; }
        set
        {
            this.middelName = value;
        }
    }
    public string LastName
    {
        get { return this.lastname; }
        set
        {
            this.lastname = value;
        }
    }

    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    public string Address
    {
        get { return address; }
        set
        {
            address = value;
        }
    }

    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }

    public string GroupName
    {
        get { return groupName; }
        set
        {
            groupName = value;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Setting DataObject

To populate labels and editors in SfDataForm, set `DataObject` property of SfDataForm.

{% tabs %}
{% highlight c# %}

dataForm.DataObject = new ContactsInfo();

{% endhighlight %}
{% endtabs %}

Now run the application to render the `SfDataForm` to edit the data object as like in below.

![](SfDataForm_images/Overview.png)

## Defining Editors

SfDataForm control generates DataFormItems (which has UI settings of data field), automatically when data object set to `SfDataForm.DataObject` property. `DataFormItem` encapsulates the layout and editor setting for a data field appearing in DataForm. When the `DataFormItems` are generated, you can handle the SfDataForm.AutoGeneratingDataFormItem event to customize or cancel the DataFormItem. 
The type of input editor generated for data field depends on the type and attribute settings of the property. The following table lists the `DataFormItem` and its constraints for generation.

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
DataFormTextItem
</td>
<td>
Generated for property of type string and any other type apart from below specified cases.
</td>
</tr>
<tr>
<td>
DataFormNumericItem
</td>
<td>
Generated for the property of type Int or Double.
[DataType(DataType.Currency)].
[DataType("Percent")]
</td>
</tr>
<tr>
<td>
DataFormDateItem
</td>
<td>
Generated for the property of type DateTime.
[DataType(DataType.Date)].
[DataType(DataType.DateTime)].
</td>
</tr>
<tr>
<td>
DataFormTimeItem
</td>
<td>
Generated for the property of type DateTime
[DataType(DataType.Time)].
</td>
</tr>
<tr>
<td>
DataFormPickerItem
</td>
<td>
Generated for the property of type enum.
[EnumDataTypeAttribute]
</td>
</tr>
</table>
Below is the list of editors supported. 
<table>
<tr>
<th>Editor</th>
<th>Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
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
Property of type Int or Double.
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
Property of type Int or Double with percent value.
[DataType("Percent")]].
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
Property of type Int or Double with currency value.
[DataType(DataType.Currency)].
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
Property of type DateTime with date value.
[DataType(DataType.Date)]
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
Property of type DateTime with time value.
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
Property of type bool
</td>
<td>
CheckBox
</td>
</tr>
<tr>
<td>
Bool
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
Property of type enum and list
[EnumDataTypeAttribute]
</td>
<td>
Spinner
</td>
</tr>
</table>

## Layout options

### Label Position

By default, DataForm arrange the label at left side and input control at the right side. You can change the label position by setting SfDataForm.LabelPosition property. You can position the label from left to top of input control by setting `LabelPosition` as Top.

{% tabs %}
{% highlight c# %}

dataForm.LabelPosition = LabelPosition.Top;

{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/LabelTop.png)

### Grid Layout

By default, DataForm arrange one data field per row. It is possible to have more than one date field per row by setting `ColumnCount` property which provide Grid like layout for DataForm.

{% tabs %}
{% highlight c# %}

dataForm.ColumnCount = 2;

{% endhighlight %}
{% endtabs %}
![](SfDataForm_images/DataFormGrid.png)

## Editing

By default, SfDataForm enable editing of data field. You can disable editing by setting `IsReadOnly` property of SfDataForm. You can enable or disable editing for particular data field by setting `IsReadOnly` property of `DataFormItem` in `AutoGeneratingDataFormItem` event. Data field editing behavior can be defined by using [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx# "") also.

