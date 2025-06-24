---
layout: post
title: Tab Items
description: About Tab items in TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Tab Items

Tab items are the individual tabs within the TabView control that contain both the header (title/icon) and the associated content. Each tab item represents a distinct section or view in your application, allowing users to navigate between different content areas seamlessly.
Tab items can be configured in the TabView through the `Items` property of `SfTabView`, which holds a collection of `SfTabItem` objects through `TabItemsCollection`.


{% tabs %}

{% highlight C# %}

var allContactsGrid = new FrameLayout(ApplicationContext);
var favoritesGrid = new FrameLayout(ApplicationContext);
var contactsGrid = new FrameLayout(ApplicationContext);
allContactsGrid.SetBackgroundColor(Color.Red);
favoritesGrid.SetBackgroundColor(Color.Green);
contactsGrid.SetBackgroundColor(Color.Blue);
var tabItems = new TabItemCollection
{
new SfTabItem()
{
Title = "Calls",
Content = allContactsGrid
},
new SfTabItem()
{
Title = "Favorites",
Content = favoritesGrid
},
new SfTabItem()
{
Title = "Contacts",
Content = contactsGrid
}
};

tabView.Items = tabItems;
SetContentView(tabView);

{% endhighlight %}

{% endtabs %}

## Share the header space equally

In order to share the header space equally for the , we can set the number of tabs which can be distributed in the available space though `VisibleHeaderCount` of SfTabView.

{% tabs %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}


