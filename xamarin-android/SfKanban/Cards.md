---
layout: post
title: Cards for Essential xamarin.android Kanban
description: Kanban Cards
platform: xamarin.android
control: Kanban
documentation: ug
---

# Cards

The default elements of a card can be customized using the following properties of [`KanbanModel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel.html):

* [`Title`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~Title.html): Sets the title of a card.
* [`ImageURL`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~ImageURL.html): Sets the image URL of a card. The image will be displayed at the right in the default card template.
* [`Category`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~Category.html): Sets the category of a card. Based on the category, the cards will be added to the respective columns.
* [`Description`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~Description.html): Sets the description text of a card.
* [`ColorKey`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~ColorKey.html): Specifies the indicator color key. The color value of the corresponding key should be added in [`IndicatorColorPalette`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~IndicatorColorPalette.html) collection of [`SfKanban`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban.html).
* [`Tags`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~Tags.html): Specifies the tags of a card. The tags will be displayed at the bottom in the default card template.
* [`ID`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanModel~ID.html): Sets the ID of a card.

{% highlight C# %}

new KanbanModel()
{
    ID = 1,
    Title = "iOS - 1002",
    ImageURL = "Image1.png",
    Category = "Open",
    Description = "Analyze customer requirements",
    ColorKey = "Red",
    Tags = new string[] { "Incident", "Customer" }
});

{% endhighlight %}

The following code sample is used to define the colors for each key.

{% highlight C# %}

List<KanbanColorMapping> colorModels = new List<KanbanColorMapping>();
colorModels.Add(new KanbanColorMapping("Green", Color.Green));
colorModels.Add(new KanbanColorMapping("Red", Color.Red));
colorModels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colorModels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.IndicatorColorPalette = colorModels;

{% endhighlight %}

![](Kanban_images/CardCustomization.png)

