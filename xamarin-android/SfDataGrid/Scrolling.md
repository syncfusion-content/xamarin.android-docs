---
layout: post
title: Scrolling | SfDataGrid | Xamarin.Android | Syncfusion
description: How to scroll the SfDataGrid.
platform: Xamarin.Android
control: SfDataGrid
documentation: ug
---

# Scrolling 

## Scrolling mode

The data grid provides three types of scrolling modes, which can be customized using the [SfDataGrid.ScrollingMode](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~SelectionMode.html) property. By default, the data grid scrolls its content based on the pixel values.

* PixelLine
* Line
* Pixel

### Pixel line

The `ScrollingMode.PixelLine` scrolls its contents like an Excel sheet. i.e., whenever a row or a column is clipped on top, the particular row or column will be auto scrolled to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

![](SfDataGrid_images/PixelLine.gif)

### Line

The `ScrollingMode.Line` scrolls its contents based on lines. i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

![](SfDataGrid_images/Line.gif)

### Pixel

The `ScrollingMode.Pixel` scrolls its contents based on pixel values. i.e., the view will update each pixel change of the offsets, and rows or columns will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

![](SfDataGrid_images/Pixel.gif)

## Programmatic scrolling

The data grid scrolls to a particular row and column index programmatically.

### Scroll to the row and column Index

Scroll programmatically to a particular row and column using the [SfDataGrid.ScrollToRowColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~ScrollToRowColumnIndex.html) method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

//For example 
dataGrid.ScrollToRowColumnIndex(20, 6);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowColumnIndex.gif)

### Scroll to the row Index

Scroll programmatically to a particular row using the [SfDataGrid.ScrollToRowIndex](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~ScrollToRowIndex.html) method by passing the row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

//For example 
dataGrid.ScrollToRowIndex(20);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowIndex.gif)

### Scroll to the column Index

Scroll programmatically to a particular column using the [SfDataGrid.ScrollToColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~ScrollToColumnIndex.html) method by passing the column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

//For example
dataGrid.ScrollToColumnIndex(7);

{% endhighlight %}

![](SfDataGrid_images/ScrollToColumnIndex.gif)

### Scroll a row/column to a specific position

The SfDataGrid allows to position the scrolled row/column in the datagrid by passing [ScrollToPosition](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.ScrollToPosition.html) as parameter to the `ScrollToRowColumnIndex`, `ScrollToRowIndex`, `ScrollToColumnIndex` methods. The scrolled row/column can take either of the four positions as explained below. The default position is `Start`.

* MakeVisible: Scroll to make a specified row/column visible in datagrid. If the specified row/column is already in view, scrolling will not occur.
* Start: Scroll to make the row/column positioned at the start of the datagrid.
* Center: Scroll to make the row/column positioned at the center of the datagrid.
* End: Scroll to make the row/column positioned at the end of the datagrid. 

N> Programmatic scrolling is not applicable for rows and columns that are frozen in view.

## Vertical over scroll mode

The [SfDataGrid.VerticalOverScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfDataGrid.Android~Syncfusion.SfDataGrid.SfDataGrid~VerticalOverScrollMode.html) property allows customizing the bouncing behavior of the data grid.

The `SfDataGrid.VerticalOverScrollMode` is of type `VerticalScrollMode` which has the following two modes:

### Bounce 

Bounce allows the data grid to have bouncing effect. The default value of `SfDataGrid.VerticalOverScrollMode` is `Bounce`. 

The following code example illustrates how to customize the bouncing effect in the data grid:

{% highlight C# %}

dataGrid.VerticalOverScrollMode = VerticalOverScrollMode.Bounce;

{% endhighlight %}

![](SfDataGrid_images/VerticalOverScrollMode_Bounce.gif)

### None

None disables the bouncing effect in the data grid.

The following code example illustrates how to customize the bouncing effect in the data grid: 
{% highlight C# %}

dataGrid.VerticalOverScrollMode = VerticalOverScrollMode.None;

{% endhighlight %}

![](SfDataGrid_images/VerticalOverScrollMode_none.gif)

