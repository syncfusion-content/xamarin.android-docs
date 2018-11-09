---
layout: post
title: Interacting with TreeView for Xamarin.Android | Syncfusion
description: Describes about the different interactions on TreeView.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Interactivity

 This section explains about how to interact with `TreeView` and its items.

## Interacting with TreeView items

### Loaded event

The [Loaded](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~Loaded_EV.html) event is raised when the TreeView is loading in view for the first time.

{% tabs %}
{% highlight c# %}
treeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, TreeViewLoadedEventArgs e)
{
    Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
    Android.App.AlertDialog alert = dialog.Create();
    alert.SetTitle("TreeView");
    alert.SetMessage("Loaded");
    alert.SetButton("OK", (c, ev) =>
    {
        // Ok button click task  
    });
    alert.Show();
}
{% endhighlight %}
{% endtabs %}
 
The `Loaded` event is used for the following use case:

* To scroll the desired item by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~NodeCollapsed_EV.html).

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~ItemTapped_EV.html) event will be triggered whenever tapping the item.  [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the tapped item as its arguments.
 * `Position`: Gets the touch position in the tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemTapped += TreeView_ItemTapped;

private void TreeView_ItemTapped(object sender, ItemTappedEventArgs e)
{
    Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
    Android.App.AlertDialog alert = dialog.Create();
    alert.SetTitle("TreeView");
    alert.SetMessage("ItemTapped");
    alert.SetButton("OK", (c, ev) =>
    {
        // Ok button click task  
    });
    alert.Show();
}

{% endhighlight %}
{% endtabs %}

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~ItemDoubleTapped_EV.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the double tapped item as its arguments.
 * `Position`: Gets the touch position in the double tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemDoubleTapped += TreeView_ItemDoubleTapped;

private void TreeView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
    Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
    Android.App.AlertDialog alert = dialog.Create();
    alert.SetTitle("TreeView");
    alert.SetMessage("ItemDoubleTapped");
    alert.SetButton("OK", (c, ev) =>
    {
        // Ok button click task  
    });
    alert.Show();
}

{% endhighlight %}
{% endtabs %}

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~ItemHolding_EV.html) event will be triggered whenever the item is long pressed.
 [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the hold item as its arguments.
 * `Position`: Gets the touch position in the hold item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemHolding += TreeView_ItemHolding;
private void TreeView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
    Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
    Android.App.AlertDialog alert = dialog.Create();
    alert.SetTitle("TreeView");
    alert.SetMessage("ItemHolding");
    alert.SetButton("OK", (c, ev) =>
    {
        // Ok button click task  
    });
    alert.Show();
}

{% endhighlight %}
{% endtabs %}