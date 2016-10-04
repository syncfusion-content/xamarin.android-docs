---
layout: post
title: Row Drag and Drop | SfDataGrid | Xamarin | Syncfusion
description:  How to enable and perform row drag and drop operation and its customization.
platform: Xamarin.Android
control: SfDataGrid
documentation: UG
---

# Row Drag and Drop

SfDataGrid allows you to drag and drop a row by setting the `SfDataGrid.AllowDraggingRow` property to `true`. A Customizable row drag and drop template is displayed  while dragging a row. The drag and drop operation can be handled based on the requirement using `SfDataGrid.QueryRowDragging` event.  

The following code example illustrates how to enable row drag and drop in SfDataGrid.

{% highlight c# %}
sfGrid.AllowDraggingRow = true;
{% endhighlight %}

## Dragging scenarios

SfDataGrid allows you to perform the drag and drop operation with both the data rows and groups.

* Records can be reordered to any positon with auto scrolling.
* Groups position can be reordered using drag and drop. But no groups can be added inside other groups. 
* Data rows can be reordered within the same group or into the other groups as well. 

N> Reordering changes are made only in `SfDataGrid.View` and not in the underlying data. Thus the changes will be reverted when performing sorting, grouping or any other operation that refreshes the view. Reordering changes in the underlying data can be achieved by handling `QueryRowDragging` event in the sample side as explained below in [Reordering underlying data](# Reordering underlying data ).

## Row drag and drop template

SfDataGrid allows you to load a desired content when performing row drag and drop operation using the `SfDataGrid.RowDragDropTemplate`. 

## Default template

Default template will be loaded, if template is not explicitly assigned for row drag and drop operations. 

![](SfDataGrid_images/RowDragAndDropDefaultTemplate.png)

## Customizing row drag and drop template

You can load any type of custom view inside `SfDataGrid.RowDragDropTemplate` based on your application’s  requirement.

Refer the following code example that shows how to load row like view in template.

{% highlight c# %}

//Assigning custom view to row drag and drop template.
sfGrid.RowDragDropTemplate = new RowDragDropTemplate(context);

{% endhighlight %}

{% highlight c# %}
//Row template a custom view which represent row.

public class RowDragDropTemplate : LinearLayout
{
    #region Fields

    Paint paint;
    Label label1;
    Label label2;
    Label label3;
    Label label4;

    #endregion

    #region Constructor

    public RowDragDropTemplate(Context context) : base(context)
    {
        this.SetWillNotDraw(false);
        paint = new Paint(PaintFlags.AntiAlias);
        paint.SetStyle(Paint.Style.Stroke);
        this.Orientation = Orientation.Horizontal;
        paint.Color = Color.Black;
        label1 = new Label(context) { Gravity = GravityFlags.Center };
        label2 = new Label(context) { Gravity = GravityFlags.Center };
        label3 = new Label(context) { Gravity = GravityFlags.Center };
        label4 = new Label(context) { Gravity = GravityFlags.Center, IsLastLabel = true };
        this.AddView(label1);
        this.AddView(label2);
        this.AddView(label3);
        this.AddView(label4);
    }

    public RowDragDropTemplate(Context context, IAttributeSet attrs) : base(context, attrs)
    {
    }

    public RowDragDropTemplate(Context context, IAttributeSet attrs, int defStyleAttr) : base(context, attrs, defStyleAttr)
    {
    }

    public RowDragDropTemplate(Context context, IAttributeSet attrs, int defStyleAttr, int defStyleRes) : base(context, attrs, defStyleAttr, defStyleRes)
    {
    }

    protected RowDragDropTemplate(IntPtr javaReference, JniHandleOwnership transfer) : base(javaReference, transfer)
    {
    }

    #endregion

    #region Methods

    protected override void OnDraw(Canvas canvas)
    {
        canvas.DrawRect(0, 0, this.Width, this.Height, paint);
        base.OnDraw(canvas);
    }

    protected override void OnLayout(bool changed, int l, int t, int r, int b)
    {
        UpdateLabelWidthAndHeight();
        base.OnLayout(changed, l, t, r, b);
        this.label1.Layout(0, 0, this.Width / 4, this.Height);
        this.label2.Layout(label1.Right, 0, (this.Width / 4) * 2, this.Height);
        this.label3.Layout(label2.Right, 0, (this.Width / 4) * 3, this.Height);
        this.label4.Layout(label3.Right, 0, (this.Width / 4) * 4, this.Height);
    }

    internal void UpdateRow(object rowData)
    {
        try
        {
            var orderInfo = rowData as OrderInfo;
            label1.Text = orderInfo.OrderID;
            label2.Text = orderInfo.EmployeeID;
            label3.Text = orderInfo.CustomerID;
            label4.Text = orderInfo.FirstName;
        }
        catch { }
    }

    internal void UpdateLabelWidthAndHeight()
    {
        label1.SetWidth(this.Width / 4);
        label2.SetWidth(this.Width / 4);
        label3.SetWidth(this.Width / 4);
        label4.SetWidth(this.Width / 4);

        label1.SetHeight(this.Height);
        label2.SetHeight(this.Height);
        label3.SetHeight(this.Height);
        label4.SetHeight(this.Height);
    }

    #endregion
}

public class Label : TextView
{
    public bool IsLastLabel { get; set; }

    public Label(Context context) : base(context)
    {
        this.SetWillNotDraw(false);
    }

    public Label(Context context, IAttributeSet attrs) : base(context, attrs)
    {
    }

    public Label(Context context, IAttributeSet attrs, int defStyleAttr) : base(context, attrs, defStyleAttr)
    {
    }

    public Label(Context context, IAttributeSet attrs, int defStyleAttr, int defStyleRes) : base(context, attrs, defStyleAttr, defStyleRes)
    {
    }

    protected Label(IntPtr javaReference, JniHandleOwnership transfer) : base(javaReference, transfer)
    {
    }

    protected override void OnDraw(Canvas canvas)
    {
        if (!IsLastLabel)
            canvas.DrawLine(this.Width - this.Resources.DisplayMetrics.Density / 2, 0, this.Width - this.Resources.DisplayMetrics.Density / 2, this.Height, new Android.Graphics.Paint() { Color = Color.Black });
        base.OnDraw(canvas);
    }
}

{% endhighlight %}

![](SfDataGrid_images/RowDragAndDrop.png)

## Row drag and drop event

`QueryRowDragging` event is fired upon starting to drag a row and will be continuously fired till the dragging ends. By handing the `SfDataGrid.QueryRowDragging` event you can also cancel the dragging of a particular row.

The `QueryRowDragging` event provides following properties in `QueryRowDraggingEventArgs`:

* `From` - Returns the index of the row currently being dragged.
* `To` – Returns the dragging index where you try to drop the row. 
* `Reason` - Returns row dragging details as `QueryRowDraggingReason`.
* `RowData` – Returns the underlying data associated with the dragged row.
* [Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs_properties(v=vs.110).aspx) – A Boolean property to cancel the event.

## How to 

### Disable dragging for particular row 

Dragging can be disabled for a particular row by handling the `QueryRowDragging` event using conditions based on `QueryRowDraggingReason`. Refer following code sample to disable dragging for particular row.

{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.From returns the index of the dragged row.
    //e.Reason returns the dragging status of the row.
    if (e.From == 1 && e.Reason == QueryRowDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}

### Disable dropping when dragging over particular rows

Dropping can be disabled for particular rows while dragging a row.Refer following code sample to cancel dropping of particular row.

{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.Reason returns the dragging status of the row.
    if ((e.To > 5 || e.To < 10) &&
    (e.Reason == QueryRowDraggingReason.DragEnded || e.Reason == QueryRowDraggingReason.Dragging))
        e.Cancel = true;
}

{% endhighlight %}

### Disable dropping of particular row 

Dropping can be canceled for particular row by handling `QueryRowDragging` event using conditions based on `QueryRowDraggingReason`. Refer following code sample to cancel dropping of particular row.

{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.From returns the index of the dragged row.
    //e.Reason returns the dragging status of the row.
    if (e.From == 1 && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}

### Disable dropping at a particular position 

Dropping at a particular position can be canceled by handling `QueryRowDragging` event using conditions based on `QueryRowDraggingReason`. Refer following code sample to cancel dropping at particular position.

{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.Reason returns the dragging status of the row.
    if ((e.To == 5 || e.To == 7) && e.Reason == QueryRowDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}

### Reordering underlying data 

Reordering changes directly on the underlying data can be done by handling `QueryRowDragging` event using conditions based on `QueryRowDraggingReason`. Refer following code sample to make permanent reordering changes.

{% highlight c# %}

private void SfGrid_QueryRowDragging(object sender, QueryRowDraggingEventArgs e)
{
    //e.To returns the index of the current row.
    //e.From returns the index of the dragged row.
    if (e.Reason == QueryRowDraggingReason.DragEnded)
    {
        var collection = (sender as SfDataGrid).ItemsSource as IList;
        collection.RemoveAt(e.From - 1);
        collection.Insert(e.To - 1, e.RowData);
    }
}

{% endhighlight %}