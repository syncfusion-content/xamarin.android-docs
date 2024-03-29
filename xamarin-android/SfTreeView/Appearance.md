---
layout: post
title: Appearance | TreeView for Xamarin.Android | Syncfusion
description: Learn here all about appearance support in Syncfusion Essential Xamarin.Android TreeView Control, its elements, and more.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Appearance in Xamarin.Android TreeView

The TreeView allows customizing appearance of the underlying data, and provides different functionalities to the end-user.

## Adapter

An Adapter can be used to present the data in a way that makes sense for the application by using different controls.

The TreeView allows you to customize the appearance of content view and expander view by setting the [Adapter](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_Adapter) property.You can customize the content view and expander view by overriding the `CreateContentView`, `CreateExpanderView` methods and update its content in the `UpdateContentView` and `UpdateExpanderView` methods of `TreeViewAdapter`.
                                      
{% tabs %}
{% highlight c# %}
protected override void OnCreate(Bundle savedInstanceState)
{
    SfTreeView treeView = new SfTreeView();
    treeView.Adapter = new CustomAdapter();
}
{% endhighlight %}
{% endtabs %}

### Creating custom Adapter

Creating a custom adapter class derived from `TreeViewAdapter`.

{% tabs %}
{% highlight c# %}
// Adapter extension class
public class CustomAdapter : TreeViewAdapter
{
    public CustomAdapter()
    {
    }

    protected override View CreateContentView(TreeViewItemInfoBase itemInfo)
    {
        var customView = new CustomContentView(TreeView.Context);
        return customView;
    }

    protected override void UpdateContentView(View view, TreeViewItemInfoBase itemInfo)
    {
        var grid = view as CustomContentView;
        var treeViewNode = itemInfo.Node;
        if (grid != null)
        {
            var icon = grid.GetChildAt(0) as ImageView;
            if (icon != null)
            {
                var imageID = (treeViewNode.Content as FileManager).ImageIcon;
                icon.SetImageResource(imageID);
            }

            var label1 = grid.GetChildAt(1) as ContentLabel;
            if (label1 != null)
            {
                label1.Text = (treeViewNode.Content as FileManager).FileName.ToString();
            }
        }
    }

    protected override View CreateExpanderView(TreeViewItemInfoBase itemInfo)
    {
        var expanderView = new ImageView(TreeView.Context);
        return expanderView;
    }

    protected override void UpdateExpanderView(View view, TreeViewItemInfoBase itemInfo)
    {
        var image = view as ImageView;
        var node = itemInfo.Node;
        if (image != null && node.HasChildNodes)
        {
            image.SetImageResource(node.IsExpanded ? Resource.Drawable.expand : Resource.Drawable.collapse);
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Android TreeView Customized adapter](Images/TreeView_CustomAdapter.png)

To create custom view to use in adapter, refer this [link](https://help.syncfusion.com/xamarin-android/sftreeview/getting-started#creating-custom-view-for-adapter).
You can also download the entire source code of this demo from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/CustomizedAdapter-1866983821)

## Indentation

The TreeView allows customizing the indent spacing of items by setting the [Indentation](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_Indentation) property. The default value of this property is `40`. This property can be customized at runtime.

{% tabs %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.Indentation = 40; 
{% endhighlight %}
{% endtabs %}

## ItemHeight

The TreeView allows customizing the height of items by setting the [ItemHeight](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ItemHeight) property. The default value of this property is `40`. This property can be customized at runtime.

{% tabs %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.ItemHeight = 40; 
{% endhighlight %}
{% endtabs %}

## ExpanderWidth

The TreeView allows customizing the width of expander view by setting the [ExpanderWidth](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ExpanderWidth) property. The default value of this property is `40`. This property can be customized at runtime.

{% tabs %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.ExpanderWidth = 40; 
{% endhighlight %}
{% endtabs %}

## ExpanderPosition

The TreeView allows you change the position of expander view by setting the [ExpanderPosition](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ExpanderPosition) property. The default value of this property is `Start`.This property has following two positions:

* `Start`: Allows displaying the expander view at the start position.
* `End`: Allows displaying the expander view at the end position.

{% tabs %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.ExpanderPosition = ExpanderPosition.End;
{% endhighlight %}
{% endtabs %}

## Level based Customization

### Level based views

The TreeView allows you to customize the content view and expander view with different views by using `CreateContentView` and `CreateExpanderView` override methods based on specific constraints.

Following example illustrates you to load different content views based on the node level.

{% tabs %}
{% highlight c# %}
// Adapter extension class
public class NodeImageAdapter : TreeViewAdapter
{
    public NodeImageAdapter()
    {
    }

    protected override View CreateContentView(TreeViewItemInfoBase itemInfo)
    {
        if (itemInfo.Node.Level == 0)
        {
            var gridView = new CustomView1(TreeView.Context);
            return gridView;
        }
        else
        {
            var gridView = new CustomView2(TreeView.Context);
            return gridView;
        }
    }

    protected override void UpdateContentView(View view, TreeViewItemInfoBase itemInfo)
    {
        var grid = view as CustomView1;
        var treeViewNode = itemInfo.Node;
        if (grid != null)
        {
            var icon = grid.GetChildAt(0) as ImageView;
            if (icon != null)
            {
                var imageID = (treeViewNode.Content as FileManager).ImageIcon;
                icon.SetImageResource(imageID);
            }

            var label1 = grid.GetChildAt(1) as ContentLabel;
            if (label1 != null)
            {
                label1.Text = (treeViewNode.Content as FileManager).FileName.ToString();
            }
            var label2 = grid.GetChildAt(2) as ContentLabel;
            label2.Text = treeViewNode.HasChildNodes ? treeViewNode.ChildNodes.Count.ToString()+" files" : "No files";
        }
        else
        {
            var grid1 = view as CustomView2;
            if (grid1 != null)
            {
                var icon = grid1.GetChildAt(0) as ImageView;
                if (icon != null)
                {
                    var imageID = (treeViewNode.Content as FileManager).ImageIcon;
                    icon.SetImageResource(imageID);
                }
                    var label1 = grid1.GetChildAt(1) as ContentLabel;
                if (label1 != null)
                {
                    label1.Text = (treeViewNode.Content as FileManager).FileName.ToString();
                }
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Android TreeView with Level based Views](Images/TreeView_LevelBasedView.png)

You can also download the entire source code of this demo from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/LevelBasedViews-1568238571)

### Level based styling.

The TreeView allows you to customize the style of `TreeViewItem` based on different levels by customizing the adapter by using `UpdateContentView` and  `UpdateExpanderView` override methods.

 You can customize the content view and expander view by overriding the `CreateContentView`, `CreateExpanderView` methods and update its content in the `UpdateContentView` and `UpdateExpanderView` methods of `TreeViewAdapter`.

{% tabs %}
{% highlight c# %}
protected override void UpdateContentView(View view, TreeViewItemInfoBase itemInfo)
{
    var grid = view as TemplateView;
    var treeViewNode = itemInfo.Node;
    var typeface = Android.Graphics.Typeface.Default;
    if (grid != null)
    {
        var label = grid.GetChildAt(0) as ContentLabel;
        if (label != null)
        {
            label.Text = (treeViewNode.Content as MailFolder).FolderName;
            if (treeViewNode.Level == 0)
            {
                label.SetTypeface(typeface, Android.Graphics.TypefaceStyle.Bold);
            }
            else
                label.SetTypeface(typeface, Android.Graphics.TypefaceStyle.Italic);
        }

        var label1 = grid.GetChildAt(1) as ContentLabel;
        if (label1 != null)
        {
            if ((treeViewNode.Content as MailFolder).MailsCount > 0)
            {
                label1.Text = (treeViewNode.Content as MailFolder).MailsCount.ToString();
                label1.SetTextColor(Android.Graphics.Color.White);
                label1.SetBackgroundColor(Android.Graphics.Color.ParseColor("#FF6377EB"));
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the example for level based styling demo from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/LevelBasedStyling-1430010482).

![Xamarin Android TreeView with styling](Images/TreeView_LevelStyle.png)

## Animation

The `SfTreeView` supports to animate expanding or collapsing the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html). To enable/disable the animation use [IsAnimationEnabled](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_IsAnimationEnabled) property of `SfTreeView`.
 
N> The default value of the `IsAnimationEnabled` property is `false`.

{% tabs %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.IsAnimationEnabled = true;
{% endhighlight %}
{% endtabs %}

![Xamarin Android TreeView with Animation](Images/TreeView_Animation.gif)
