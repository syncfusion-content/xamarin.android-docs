---
layout: post
title: Selection | SfDataGrid | Xamarin.Android | Syncfusion
description: How to enable selection, about the selection modes, properties, events and customizations available for selection in a SfDataGrid.
platform: Xamarin.Android
control: SfDataGrid
documentation: UG
---

# Selection

This section explains how to enable selection in the data grid and the selection modes, properties, events involved in selection and customizations available for selection in the data grid.

The data grid selects a specific row or group of rows either programmatically or by touch interactions. To enable the selection in the data grid, set the [SfDataGrid.SelectionMode](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionMode.html) property to `None`. The data grid has different selection modes to perform selection operation as listed as follows:

## Selection modes 

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[None](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }} </td>
<td>Disables selection and no rows can be selected. This is the default value.</td>
</tr>
<tr>
<td> {{'[Single](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }} </td>
<td> Selects a single row. Upon selecting the next row the selection in the previous row is cleared. </td>
</tr>
<tr>
<td> {{'[Multiple](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }}  </td>
<td> Selects more than one row. The selection is not cleared when selecting more than one records. When you click on a selected row for the second time, the selection will be cleared. </td>
</tr>
<tr>
<td>  {{'[SingleDeselect](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SelectionMode.html)'| markdownify }}  </td>
<td> Selects only a single row. However, upon tapping the row again the selection is cleared. Similar to the single mode, upon selecting the next row the selection in the previous row is cleared. </td>
</tr>
</table>

The following code example illustrates how to set the selection mode in the data grid:

{% highlight c# %}
dataGrid.SelectionMode = SelectionMode.Multiple; 
{% endhighlight %}

## Programmatic selection

When the `SfDataGrid.SelectionMode` is set as `None`, select the row/rows in the data grid from the code by setting the [SfDataGrid.SelectedIndex](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectedIndex.html), [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectedItem.html), or [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectedItems.html) property based on the selection mode. The following code example illustrates how to enable selection from code in the data grid:

When the selection mode is `single`, programmatically select a row in two ways, either by setting the row index to the `SfDataGrid.SelectedIndex` property or by setting the underlying object to be selected to the `SfDataGrid.SelectedItem` property. 

The following code example illustrates how to programmatically select a row from the code:

{% highlight c# %}
//Perform selection using selected index
dataGrid.SelectedIndex = 3;
 
//Perform selection using selected item
dataGrid.SelectedItem = viewModel.OrdersInfo [5];
{% endhighlight %}

When the selection mode is multiple, programmatically select more than one row by adding the underlying object to be selected to the `SfDataGrid.SelectedItems` property. 

The following code example illustrates how to programmatically select more than one rows from the code.

{% highlight c# %} 
//Perform multiple selection using selected item
dataGrid.SelectedItems.Add (viewModel.OrdersInfo [4]);
dataGrid.SelectedItems.Add (viewModel.OrdersInfo [5]);
{% endhighlight %}

The following screenshot shows the selection functionality in SfDataGrid.
![](SfDataGrid_images/Selection.png)

### Current item

The [SfDataGrid.CurrentItem](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~CurrentItem.html) property holds the underlying data of the last selected row in the data grid. 

Get the current item in the `SfDataGrid.SelectionChanged` event, by setting the `SfDataGrid.SelectionMode` as `Multiple` or `SingleDeselect`. If the `SelectionMode` is `single` the currentItem and selectedItem are same.

The following code example illustrates how to set the selection mode for the data grid in the SelectionChanged event.

{% highlight c# %}
dataGrid.SelectionMode = SelectionMode.Multiple; 
 
dataGrid.SelectionChanged += DataGrid_SelectionChanged; 
 
void DataGrid_SelectionChanged (object sender, GridSelectionChangedEventArgs e) 
{ 
 var currentItem = dataGrid.CurrentItem; 

 //your codes
} 
{% endhighlight %}

## Selection events

The data grid provides the following events for the selection:

* [SelectionChanging](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionChanging_EV.html): This event is raised while selecting a row at the execution time. Hence, it allows canceling the selection action by setting the Cancel property of [GridSelectionChangingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.GridSelectionChangingEventArgs.html).
* [SelectionChanged](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionChanged_EV.html): This event is raised after the column is selected.

These two events are triggered with `GridSelectionChangingEventArgs` and [GridSelectionChangedEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.GridSelectionChangedEventArgs.html) that contains the following properties:

* AddedItems: Gets the collection of the underlying data objects added to selection.
* RemovedItems: Gets the collection of the underlying data objects removed from selection.

The following code example illustrates how to hook the `SfDataGrid.SelectionChanging` event and cancel the selection of a column:

{% highlight c# %}
dataGrid.SelectionChanging += DataGrid_SelectionChanging;  

void DataGrid_SelectionChanging (object sender, GridSelectionChangingEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}

The following code explains how to get the selected item in code-behind by making use of the `SfDataGrid.SelectionChanged` event:

{% highlight c# %} 
dataGrid.SelectionChanged += DataGrid_SelectionChanged; 

private void DataGrid_SelectionChanged (object sender, GridSelectionChangedEventArgs e) 
{ 
    // Gets the selected item.
    var selectedItems = e.AddedItems[0]; 
} 
{% endhighlight %} 

## Row header selection

The data grid selects the grid row(s) upon tapping over the grid cells. It also allows selecting the grid rows when tapping the row header cells. To enable selection in the data grid, set the [SfDataGrid.SelectionMode](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionMode.html) property to `None`.

### Select records in the data grid when tapping only on the row header cells

The data grid allows selecting a specific row or group of rows by touching the grid cells. However, to select the record only when tapping on the row header cells, use `SfDataGrid.SelectionChanging` event. 
 
The following code example illustrates how to select records in the data grid when tapping only on the row header cells:

{% highlight c# %}

dataGrid.SelectionMode = SelectionMode.Single;

private void DataGrid_SelectionChanging(object sender, GridSelectionChangingEventArgs e)
{
    e.Cancel = true;
}

private void DataGrid_GridTapped(object sender, GridTappedEventsArgs e)
{
    if(e.RowColumnIndex.ColumnIndex == 0)
    {
        dataGrid.SelectedIndex = e.RowColumnIndex.RowIndex;
    }
}
 
{% endhighlight %}

N> To enable the row header in the data grid, set the `SfDataGrid.ShowRowHeader` to `true`.


## Clear selection

The data grid allows clearing the selection applied in the grid rows in two ways, either by setting the `SfDataGrid.SelectionMode` to `None` or by calling the [SfDataGrid.SelectionController.ClearSelection ()](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.GridSelectionController~ClearSelection.html) method.

The following code example illustrates how to clear selection in the data grid:

{% highlight c# %}
//Clear selection using selection mode
dataGrid.SelectionMode = SelectionMode.None;

//Clear selection using selection controller
dataGrid.SelectionController.ClearSelection (); 
{% endhighlight %}

N> Selected items and the selections will be cleared whenever the ItemsSource changed at runtime.

## Multiple selection colors

The data grid supports selecting one or more rows either programmatically or by touch interactions. By default, the data grid applies a common background color for the selected rows based on the current theme. However, it also provides extensibility to have multiple selection colors when touching the rows by writing a custom [SelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionController.html) derived from [GridSelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.GridSelectionController.html) and, assigning it to the `SfDataGrid.SelectionController` property. Override the GetSelectionColor() method to apply different colors for selection at runtime.

The following code example illustrates how to set different colors for the selected rows in the data grid:

{% highlight c# %}
sfGrid.SelectionController = new CustomSelectionController(sfGrid);
sfGrid.SelectionMode = SelectionMode.Multiple;
{% endhighlight %}

{% highlight c# %}
public class CustomSelectionController : GridSelectionController
{
    public Color[] SelectionColors { get; set; }

    public CustomSelectionController(SfDataGrid datagrid)
    {
        this.DataGrid = datagrid;
        SelectionColors = new Color[11] 
        { 
            Color.DarkSalmon,
            Color.DarkSlateGray,
            Color.Red, 
            Color.Blue,
            Color.DarkOliveGreen, 
            Color.Black, 
            Color.Gray, 
            Color.MediumPurple,
            Color.BurlyWood,
            Color.DarkCyan,
            Color.DarkGoldenrod 
        };   
    }
    //Code to set multiple selection colors
    public override Color GetSelectionColor(int rowIndex, object rowData)
    {
        if (SelectionColors != null)
            return SelectionColors[rowIndex % 11];
        else
            return Color.Blue;
    }
}
{% endhighlight %}

The following screenshot shows the outcome upon execution of the above code:

![](SfDataGrid_images/MultipleSelectionColors_img1.jpeg)

## Selection animation

The data grid supports selecting one or more rows programmatically or by touch interactions. In addition, the data grid also provides extensibility to animate the selected rows. 

It can be done by extending the [GridSelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.GridSelectionController.html ).

Refer the below example in which a CustomSelectionController derived from `GridSelectionController` and an instance of it is assigned to the [SfDataGrid.SelectionController](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfdatagrid/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionController.html ) property to achieve selection animation.

{% highlight c# %}
dataGrid.SelectionController = new CustomSelectionController(dataGrid);
dataGrid.SelectionMode = SelectionMode.Multiple;
{% endhighlight %}

{% highlight c# %}
public class CustomSelectionController : GridSelectionController
{
    public CustomSelectionController(SfDataGrid sfGrid)
    {
        this.DataGrid = sfGrid;
    }
    protected override void SetSelectionAnimation(VirtualizingCellsControl rowElement)
    {
        rowElement.Alpha = 0.5f;
        rowElement.Animate().Alpha(0.5f).SetDuration(1000).AlphaBy(1f).WithEndAction(new Runnable(() =>
        {
            rowElement.Alpha = 1f;
        }));
    }
}
{% endhighlight %}

The following screenshot shows the selection animation in the data grid:

![](SfDataGrid_images/Selection-Animation.gif)