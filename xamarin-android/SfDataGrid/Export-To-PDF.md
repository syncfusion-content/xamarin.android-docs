---
layout: post
title: Exporting | SfDataGrid | Xamarin.Android | Syncfusion
description: How to export a SfDataGrid to PDF and it's customizations.
platform: Xamarin.Android
control: SfDataGrid
documentation: ug
---

# Exporting

The SfDataGrid supports exporting the data to PDF with several customization options like custom appearance, excluding specific columns, excluding headers, setting custom row height, setting custom column width, etc. It also supports [Grouping](https://help.syncfusion.com/xamarin-android/sfdatagrid/grouping), [Filtering](https://help.syncfusion.com/xamarin-android/sfdatagrid/filtering) and [Sorting](https://help.syncfusion.com/xamarin-android/sfdatagrid/sorting) when exporting.

The following assemblies should be added for exporting to PDF file.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>android</td>
<td>android\Syncfusion.SfGridConverter.Android.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>

The following code explains how to create and display a SfDataGrid in view.

{% tabs %}
{% highlight c# %}
// In MainActivity.cs

SfDataGrid sfGrid;
LinearLayout layout;
Button btn1;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);

    sfGrid = new SfDataGrid(BaseContext);
    sfGrid.AutoGenerateColumns = false;
    sfGrid.ItemsSource = new ViewModel().OrdersInfo;

    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "FirstName" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "Freight", HeaderText = "Freight" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "LastName" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "ShipCity", HeaderText = "City" });
    sfGrid.Columns.Add(new GridTextColumn() { MappingName = "IsClosed" });

    btn1 = new Button(BaseContext);
    btn1.Text = "Export To Pdf";
    btn1.Click += ExportToPdf_Clicked;

    layout = new LinearLayout(BaseContext);
    layout.Orientation = Orientation.Vertical;
    layout.AddView(sfGrid, LinearLayout.LayoutParams.MatchParent,1500);
    layout.AddView(btn1, LinearLayout.LayoutParams.MatchParent, 200);
 
    SetContentView(layout);
}
{% endhighlight %}
{% endtabs %}

## Export to PDF

You can export data to PDF by using the [DataGridPdfExportingController.ExportToPdf](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportingController~ExportToPdf.html) method by passing the SfDataGrid as an argument. 

{% tabs %}
{% highlight c# %}
private void ExportToPdf_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    var doc = pdfExport.ExportToPdf(this.sfGrid);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/PDFExport.png)

## Exporting Options

### Exclude Columns while Exporting

By default, all the columns (including hidden columns) in the SfDataGrid will be exported to PDF. To exclude some particular columns while exporting to PDF, add those columns to the [DataGridPdfExportOption.ExcludeColumns](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExcludeColumns.html) list.

{% tabs %}
{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
DataGridPdfExportOption exportOption = new DataGridPdfExportOption ();
exportOption.FitAllColumnsInOnePage = true;
var list = new List<string>();
list.Add("OrderID");
list.Add("LastName");
exportOption.ExcludedColumns = list;
var doc = pdfExport.ExportToPdf (this.dataGrid, exportOption); 
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/ExcludeColumn.png)

### PdfDocument

The [DataGridPdfExportOption.PdfDocument](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~PdfDocument.html) allows exporting the SfDataGrid to an existing or new PdfDocument. 

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
PdfDocument pdfDocument = new PdfDocument();
pdfDocument.Pages.Add();
pdfDocument.Pages.Add();
pdfDocument.Pages.Add();
option.StartPageIndex = 1;
option.PdfDocument = pdfDocument;
{% endhighlight %}
{% endtabs %}

### RepeatHeaders

You can show or hide the column headers on each page of the exported PDF document by using the [DataGridPdfExportOption.RepeatHeaders](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~RepeatHeaders.html) property. The default value is true.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.RepeatHeaders = true;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

### Exclude Groups while Exporting

By default, all the groups in the data grid will be exported to PDF document. To export the data grid without Groups, set the [DataGridPdfExportOption.ExportGroups](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportGroups.html) property to `false`.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.ExportGroups = false;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/ExcludeColumn.png)

### Exclude Column Header while Exporting

By default, the column headers will be exported to PDF document. To export the SfDataGrid without the column headers, set the [DataGridPdfExportOption.ExportHeader](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportHeader.html) to `false`.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.ExportHeader = false;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/ExcludeHeader.png)

### Exclude Table Summaries while Exporting

By default, the table summaries in data grid will be exported to excel. To export the SfDataGrid without the table summaries, set the [DataGridPdfExportOption.ExportTableSummary](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportTableSummary.html) property to `false`.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.ExportTableSummary = true;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/SymmaryPDF.png)

### Exporting SfDataGrid from Particular Starting Page

The SfDataGrid allows exporting the data from a particular staring position using the following options:

* StartPageIndex
* StartPoint 

#### StartPageIndex 

The SfDataGrid allows exporting the data to a particular starting page by using the [DataGridPdfExportOption.StartPageIndex](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~StartPageIndex.html) property.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    PdfDocument pdfDocument = new PdfDocument();
    pdfDocument.Pages.Add();
    pdfDocument.Pages.Add();
    pdfDocument.Pages.Add();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.PdfDocument = pdfDocument;
    option.StartPageIndex = 1;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/StartIndex.png)

#### StartPoint

The SfDataGrid allows exporting the data to a particular x,y starting point in the PDF page by using the [DataGridPdfExportOption.StartPoint](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~StartPoint.html) property.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.StartPoint = new PointF(0, 500);
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Startpoint.png)

### ApplyGridStyle

The SfDataGrid allows exporting the data with the applied GridStyle by setting the [DataGridPdfExportOption.ApplyGridStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ApplyGridStyle.html) to `true`. By default, data will be exported without the GridStyle.

{% tabs %}
{% highlight c# %}
private void PDFExport_Clicked(object sender, EventArgs e)
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
    MemoryStream stream = new MemoryStream();
    DataGridPdfExportOption option = new DataGridPdfExportOption();
    option.ApplyGridStyle = true;
    var doc = pdfExport.ExportToPdf(this.sfGrid,option);
    doc.Save(stream);
    doc.Close(true);
    Save("DataGrid.pdf", "application/pdf", stream, sfGrid.Context);
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/GridStyle.png)

The SfDataGrid also allows customizing the following styles while exporting to PDF:

* BottomTableSummaryStyle 
* GroupCaptionStyle
* HeaderStyle
* RecordStyle 
* TopTableSummaryStyle

#### BottomTableSummaryStyle

The SfDataGrid supports exporting the bottom TableSummary with custom style by using the [DataGridPdfExportOption.BottomTableSummaryStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~BottomTableSummaryStyle.html) property.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.BottomTableSummaryStyle = new PdfGridCellStyle()
{
    BackgroundBrush = PdfBrushes.Black,
    Borders = new PdfBorders() { Bottom = PdfPens.Aqua, Left = PdfPens.AliceBlue, Right = PdfPens.Red, Top = PdfPens.RoyalBlue },
    CellPadding = new PdfPaddings(2, 2, 2, 2),
    TextBrush = PdfBrushes.Pink,
    TextPen = PdfPens.Aqua,
    StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Right, CharacterSpacing = 3f, WordSpacing = 10f }
};
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Bottom_SummaryStyle.png)

#### GroupCaptionStyle

The SfDataGrid supports exporting the GroupCaptionSummaries with custom style by using the [DataGridPdfExportOption.GroupCaptionStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GroupCaptionStyle.html) property.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.GroupCaptionStyle = new PdfGridCellStyle()
{
    BackgroundBrush = PdfBrushes.Aqua,
    Borders = new PdfBorders() { Bottom = PdfPens.Aqua, Left = PdfPens.AliceBlue, Right = PdfPens.Red, Top = PdfPens.RoyalBlue },
    CellPadding = new PdfPaddings(2, 2, 2, 2),
    TextBrush = PdfBrushes.RosyBrown,
    TextPen = PdfPens.Black,
    StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Right, CharacterSpacing = 3f, WordSpacing = 10f }
};
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Summary_Style.png)

#### HeaderStyle

The SfDataGrid allows exporting the column headers with custom style by using the [DataGridPdfExportOption.HeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~HeaderStyle.html) property.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.HeaderStyle = new PdfGridCellStyle()
{
    BackgroundBrush = PdfBrushes.Black,
    Borders = new PdfBorders() { Bottom = PdfPens.Aqua, Left = PdfPens.AliceBlue, Right = PdfPens.Red, Top = PdfPens.RoyalBlue },
    CellPadding = new PdfPaddings(2,2,2,2),
    TextBrush = PdfBrushes.Green,
    TextPen = PdfPens.Aqua,
    StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Left, CharacterSpacing = 3f, WordSpacing = 10f }
};
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/RecordHeaderStyle.png)

#### RecordStyle 

SfDataGrid allows exporting the records with custom style by using the [DataGridPdfExportOption.RecordStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~RecordStyle.html) property.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.RecordStyle = new PdfGridCellStyle()
{
    BackgroundBrush = PdfBrushes.Green,
    Borders = new PdfBorders() { Bottom = PdfPens.Aqua, Left = PdfPens.AliceBlue, Right = PdfPens.Red, Top = PdfPens.RoyalBlue },
    CellPadding = new PdfPaddings(2, 2, 2, 2),
    TextBrush = PdfBrushes.Gray,
    TextPen = PdfPens.Black,
    StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Right, CharacterSpacing = 3f, WordSpacing = 10f }
};
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/RecordHeaderStyle.png)

#### TopTableSummaryStyle

The SfDataGrid supports exporting the top TableSummary with custom style by using the [DataGridPdfExportOption.TopTableSummaryStyle](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~TopTableSummaryStyle.html) property.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.TopTableSummaryStyle = new PdfGridCellStyle()
{
    BackgroundBrush = PdfBrushes.Pink,
    Borders = new PdfBorders() { Bottom = PdfPens.Aqua, Left = PdfPens.AliceBlue, Right = PdfPens.Red, Top = PdfPens.RoyalBlue },
    CellPadding = new PdfPaddings(2, 2, 2, 2),
    TextBrush = PdfBrushes.Green,
    TextPen = PdfPens.Green,
    StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Right, CharacterSpacing = 3f, WordSpacing = 10f }
};
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Summary_Style.png)

### Customizing Borders

The SfDataGrid allows customizing the grid borders by using the `GridLineType` property as follows:

* Both
* Horizontal
* Vertical
* None

#### Both

Set the [DataGridPdfExportOption.GridLineType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GridLineType.html) to `GridLineType.Both` to export the data grid with both horizontal and vertical borders.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.GridLineType = GridLineType.Both;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/AllLine.png)

#### Horizontal

Set the [DataGridPdfExportOption.GridLineType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GridLineType.html) to `GridLineType.Both` to export the data grid with horizontal border only.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.GridLineType = GridLineType.Horizontal;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Horizontal.png)

#### Vertical

Set the [DataGridPdfExportOption.GridLineType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GridLineType.html) to `GridLineType.Both` to export the data grid with vertical border only.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.GridLineType = GridLineType.Vertical;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Verticalline.png)

#### None

Set the [DataGridPdfExportOption.GridLineType](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~GridLineType.html) to `GridLineType.Both` to export the data grid without any borders.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.GridLineType = GridLineType.None;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/LineNone.png)

### ExportAllPages

While exporting to excel using the SfDataPager inside the SfDataGrid, by default it will be export only the current page. However, you can export all the pages by setting the [DataGridPdfExportOption.ExportAllPages](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportAllPages.html) to `true`. The default value of this property is false.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.ExportAllPages = true;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/AllPageExport.png)

* ExportAllPages is false

![](SfDataGrid_images/PDF/CurrentPage.png)

### ExportColumnWidth

By default, the data grid columns will be exported to Excel with the value of the `DataGridPdfExportOption.DefaultColumnWidth` but, you can also export the data grid to Excel with the exact column widths from the SfDataGrid by setting the [DataGridPdfExportOption.ExportColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportColumnWidth.html) to `true`. The default value of `ExportColumnWidth` property is false.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.ExportColumnWidth = true;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/LineNone.png)

### ExportRowHeight

By default, the data grid rows will be exported to Excel with the value of the `DataGridPdfExportOption.DefaultRowHeight` but, you can also export the data grid to Excel with the exact row heights from the SfDataGrid by setting the [DataGridPdfExportOption.ExportRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~ExportRowHeight.html) to `true`. The default value of `ExportRowHeight` property is false.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.ExportRowHeight = true;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/PDFExport.png)

### DefaultColumnWidth

The SfDataGrid allows customizing the column width in Excel file using the [DataGridPdfExportOption.DefaultColumnWidth](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~DefaultColumnWidth.html) property. The `DefaultColumnWidth` value will be applied to all the columns in the Excel sheet.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.DefaultColumnWidth = 100;
{% endhighlight %}
{% endtabs %}

### DefaultRowHeight

The SfDataGrid allows customizing the row height in Excel file by using the [DataGridPdfExportOption.DefaultRowHeight](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportOption~DefaultRowHeight.html) property. The `DefaultRowHeight` value will be applied to all the rows in the Excel sheet.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
option.DefaultRowHeight = 20;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/DefaultColumn.png)

### PDF Page Orientation Change

You can change the page orientation of PDF document while exporting. The default page orientation is Portrait.

To change the page orientation, export the PdfGrid value by using the ExportToPdfGrid method, and then draw that PdfGrid into a PdfDocument by changing the `PageSettings.Orientation` property of PdfDocument.

{% tabs %}
{% highlight c# %}
DataGridPdfExportOption option = new DataGridPdfExportOption();
PdfDocument pdfDocument = new PdfDocument();
pdfDocument.PageSettings.Orientation = PdfPageOrientation.Landscape;
//pdfDocument.PageSettings.Orientation = PdfPageOrientation.Portrait;
option.PdfDocument = pdfDocument;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Landscape.png)

### Setting Header and Footer

The SfDataGrid provides displaying additional content at the top (Header) or bottom (Footer) of the page while exporting to PDF by handling the `DataGridPdfExportingController.HeaderAndFooterExporting` event.

You can insert the string in header and footer in PdfHeaderFooterEventHandler. Setting `PdfPageTemplateElement` to `PdfHeaderFooterEventArgs.PdfDocumentTemplate.Top` loads the content at top of the page, and setting the `PdfPageTemplateElement` to  `PdfHeaderFooterEventArgs.PdfDocumentTemplate.Bottom` loads the content at bottom of the page.

{% tabs %}
{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
pdfExport.HeaderAndFooterExporting += PdfExport_HeaderAndFooterExporting;

private void PdfExport_HeaderAndFooterExporting(object sender, PdfHeaderFooterEventArgs e)
{
    PdfFont font = new PdfStandardFont(PdfFontFamily.TimesRoman, 20f, PdfFontStyle.Bold);
    var width = e.PdfPage.GetClientSize().Width;
    PdfPageTemplateElement header = new PdfPageTemplateElement(width, 38);
    header.Graphics.DrawString("Order Details", font, PdfPens.Black, 70, 3);
    e.PdfDocumentTemplate.Top = header;

    PdfPageTemplateElement footer = new PdfPageTemplateElement(width, 38);
    footer.Graphics.DrawString("Order Details", font, PdfPens.Black, 70, 3);
    e.PdfDocumentTemplate.Bottom = footer;
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/HeaderFooter.png)

## Save a File

The following code snippet explains how to save the converted PDF document in our local device.

{% tabs %}
{% highlight c# %}
public void Save(string fileName, String contentType, MemoryStream stream,Context context)
{
    string exception = string.Empty;
    string root = null;
    if (Android.OS.Environment.IsExternalStorageEmulated)
    {
        root = Android.OS.Environment.ExternalStorageDirectory.ToString();
    }
    else
        root = System.Environment.GetFolderPath(System.Environment.SpecialFolder.MyDocuments);

        Java.IO.File myDir = new Java.IO.File(root + "/Syncfusion");
        myDir.Mkdir();

        Java.IO.File file = new Java.IO.File(myDir, fileName);

        if (file.Exists())
        {
            file.Delete();
            file.CreateNewFile();
        }
        try
        {
            FileOutputStream outs = new FileOutputStream(file, false);
            outs.Write(stream.ToArray());

            outs.Flush();
            outs.Close();
        }
        catch (Exception e)
        {
            exception = e.ToString();
        }
        if (file.Exists() && contentType != "application/html")
        {
            Android.Net.Uri path = Android.Net.Uri.FromFile(file);
            string extension = Android.Webkit.MimeTypeMap.GetFileExtensionFromUrl(Android.Net.Uri.FromFile(file).ToString());
            string mimeType = Android.Webkit.MimeTypeMap.Singleton.GetMimeTypeFromExtension(extension);
            Intent intent = new Intent(Intent.ActionView);
            intent.SetDataAndType(path, mimeType);
            this.StartActivity(Intent.CreateChooser(intent, "Choose App"));
        }
}
{% endhighlight %}
{% endtabs %}

## Events

The SfDataGrid provides you the following events for `Exporting`:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportingController~RowExporting_EV.html): Raised while exporting a row at the execution time.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridPdfExportingController~CellExporting_EV.html): Raised while exporting a cell at the execution time.

### RowExporting

The [DataGridRowPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventhandler.html) delegate allows customizing the styles for record rows and group caption rows. The`RowExporting` event is triggered with [DataGridRowPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs.html) that contains the following properties:

* [PdfGrid](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs~PdfGrid.html): Customizes the properties of pdfGrid such as `Background`, `CellPadding`, `CellSpacing`, etc.
* [PdfRow](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs~PdfRow.html): Specifies the `PdfGridRow` to be exported. You can use this to customize the properties of a particular row. 
* [Record](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs~Record.html): Gets the collection of exported underlying data objects.
* [RowType](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridRowPdfExportingEventArgs~RowType.html): Specifies the row type by using `ExportRowType` `Enum`. You can use this property to check the row type and apply different styles based on the row type.

You can use this event to customize the properties of the grid rows exported to PDF. The following code example illustrates how to change the background color of the record rows and caption summary rows while exporting.

{% tabs %}
{% highlight c# %}
//HandlingRowExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.RowExporting += pdfExport_RowExporting; 

void pdfExport_RowExporting (object sender, DataGridRowPdfExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGreen;
    }

    if (e.RowType == ExportRowType.CaptionSummary) {
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGray;
    }
} 
{% endhighlight %}
{% endtabs %}

#### CellExporting

The [DataGridCellPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventhandler.html) delegate allows customizing the styles for header cells, record cells, and group caption cells. The `CellExporting` event is triggered with [DataGridCellPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs.html) that contains the following properties:

* [CellType](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~CellType.html): Specifies the cell type by using `ExportCellType` `Enum`. You can use this property to check the cell type and apply different cell styles based on the cell type.
* [CellValue](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~CellValue.html): Contains the actual value exported to the PDF. You can use this value to apply formatting in PDF using `Range` property.
* [ColumnName](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~ColumnName.html): Specifies the column name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the `ColumnName`.
* [Handled](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~Handled.html): Determines whether the cell is exported to PDF or not.
* [PdfGrid](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~PdfGridCell.html): Specifies the `PDFGridCell` to be exported. You can use this to customize the properties (Background, Foreground, Font, Alignment, etc.) of a particular cell.
* [Record](http://help.syncfusion.com/cr/cref_files/xamarin-android/sfgridconverter/Syncfusion.SfGridConverter.Android~Syncfusion.SfDataGrid.Exporting.DataGridCellPdfExportingEventArgs~Record.html): Gets the collection of the exported underlying data objects.

You can use this event to customize the properties of the grid cells exported to PDF. The following code example illustrates how to customize the background color, foreground color, and cell value of the header cells, record cells, and caption summary cells while exporting.

{% tabs %}
{% highlight c# %}
//HandlingCellExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.CellExporting += pdfExport_CellExporting;  

void pdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell)
    {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Blue;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.White;
    }

    if (e.CellType == ExportCellType.RecordCell)
    {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Yellow;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Black;
        e.PdfGridCell.Style.Borders = new PdfBorders() {Bottom = PdfPens.Green, Top = PdfPens.Red,Left = PdfPens.Blue,Right = PdfPens.Brown};
    }

    if (e.CellType == ExportCellType.GroupCaptionCell)
    {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.LightGray;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Blue;
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/CellExporting.png)

## Embedding Fonts in PDF File

By default, some fonts (such as Unicode font) are not supported in PDF. In this case, it is possible to embed the font in PDF document with the help of PdfTrueTypeFont.

{% tabs %}
{% highlight c# %}
Stream fontStream = typeof(MainActivity).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Pacifico.ttf");
private void PdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellValue != null)
    {
        PdfFont font = e.PdfGridCell.Style.Font;
        if (font != null)
        {
            PdfTrueTypeFont unicodeFont = new PdfTrueTypeFont(fontStream, font.Size, font.Style);
            e.PdfGridCell.Style.Font = unicodeFont;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Fontstyle.png)

## Customize Cell Values while Exporting

You can customize the call values while exporting to PDF by handling the `CellExporting` event.

{% tabs %}
{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
pdfExport.CellExporting += PdfExport_CellExporting;
private void PdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "IsClosed")
    {
        if ((bool)e.CellValue)
            e.CellValue = "Y";
        else
            e.CellValue = "N";
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/CellValueChange.png)

## Changing Row Style in PDF Based on Data

You can customize the row style based on the data while exporting to PDF by handling `RowExporting` event.

{% tabs %}
{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
pdfExport.RowExporting += PdfExport_RowExporting;
private void PdfExport_RowExporting(object sender, DataGridRowPdfExportingEventArgs e)
{
    if (!(e.Record.Data is OrderInfo))
        return;

    if (e.RowType == ExportRowType.Record)
    {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.PdfRow.Style.BackgroundBrush = PdfBrushes.Yellow;
        else
            e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGreen;
    }
}
{% endhighlight %}
{% endtabs %}

## Customize the Cells Based on Column Name

You can customize the column style based on the data while exporting to PDF by handling the `CellExporting` event.

{% tabs %}
{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController();
pdfExport.CellExporting += PdfExport_CellExporting;
private void PdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "FirstName")
    {
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Red;
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/PDF/Fontstyle.png)

## Exporting Unbound Columns

The `SfDataGrid.GridUnboundColumns` will be exported as `SfDataGrid.GridTextColumns` without any specific codes. You can customize the `SfDataGrid.GridUnboundColumns` as `SfDataGrid.GridTextColumns` using the `CellExporting` and `RowExporting` events.

{% tabs %}
{% highlight c# %}
var unboundColumn = new GridUnboundColumn()
{
    MappingName = "Unbound",
    Expression = "OrderID",
};

sfGrid.Columns.Add(unboundColumn);
{% endhighlight %}
{% endtabs %}

The below screenshot shows that the unbound column is exported to PDF document along with text columns.

![](SfDataGrid_images/Exporting_img7.png)

