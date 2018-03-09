---
layout: post
title:  Custom Header
description: Custom Header in Syncfusion TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Custom Header 

When the built-in view is not needed, it can be overridden by adding the custom view to the header region of a tab. 

{% tabs %}

{% highlight C# %}

Button allCallsButton = new Button(context);
allCallsButton.Text = "All Calls";
allCallsButton.SetBackgroundColor(Android.Graphics.Color.Yellow);
allCallsButton.Clicked += AllCallsButton_Clicked;
var tabViewItem = new SfTabItem()
{
Title = "Calls",
Content = allContactsGrid,
HeaderContent = allCallsButton
};
			
{% endhighlight %}

{% endtabs %}

## How to handle the events for custom view with tab view?

When you use the button or similar control with clicked event, it can be handled directly and set to the `SelectedIndex` property to navigate the clicked view.

{% highlight C# %}

private void Button_Clicked(object sender, System.EventArgs e)
{
tabView.SelectedIndex = 0;
}
			
{% endhighlight %}

