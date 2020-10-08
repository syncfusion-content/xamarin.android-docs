---
layout: post
title: Working with Xamarin.Android TreeView | Syncfusion
description: This topic describes how to use Syncfusion Xamarin.Android TreeView along with interacting events and other different functionalities
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Working with TreeView in Xamarin.Android TreeView (SfTreeView)

## Interacting with TreeView Items

### To update the Runtime changes

The [PropertyChanged](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PropertyChanged) event will be triggered whenever a properties in TreeViewNode is changed. You can get the name of the property that changed by using the `PropertyName` property of the `PropertyChangedEventArgs`.

{% tabs %}
{% highlight c# %}
treeviewnode.PropertyChanged += Treeviewnode_PropertyChanged;

private void Treeviewnode_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (treeviewnode.IsExpanded)
        DisplayAlert("treeview", "nodeexpanded", "ok");
    else
        DisplayAlert("treeview", "nodecollapsed", "ok");
}
{% endhighlight %}
{% endtabs %}

## Refresh layout

[SetDirty](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_SetDirty) notifies the TreeViewNode to recalculate the child collection update mechanism to invalidate that node which helps to update the engine and refresh the UI.

{% endhighlight %}
{% highlight c# %}
node.SetDirty();
{% endhighlight %}
{% endtabs %}

