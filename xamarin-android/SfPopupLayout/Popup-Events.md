---
layout: post
title: Popup Events| SfPopupLayout |Xamarin.Android| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening Event

[SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is opening in the application with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup opening.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Opening` event.

{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Opening += PopupLayout_Opening;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}

## Opened Event

[SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever the PopupView is displayed in the application.
You can write your set of codes that needs to be executed once the popup is opened and visible in the application, in the respective event handler.

Refer to the following code example for using `SfPopupLayout.Opened` event.

{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Opened += PopupLayout_Opened;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
    // You can write your set of codes that needs to be executed once the popup is opened and visible in the application, in the respective event handler.
}
{% endhighlight %}

## Closing Event

[SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Closing_EV.html) event will be fired whenever the PopupView is about to be closed in the application with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Closing` event.

{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Closing += PopupLayout_Closing;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}

## Closed Event

[SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever the PopupView is dismissed from the view.
You can write your set of codes that needs to be executed once the popup is completely closed, in the respective event handler.

Refer to the following code example for using `SfPopupLayout.Closed` event.

{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Closed += PopupLayout_Closed;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    // You can write your set of codes that needs to be executed once the popup is completely closed, in the respective event handler.
}
{% endhighlight %}

## Footer Button Clicked Events

Following are the two events available in the Footer.

* AcceptButtonClicked
* DeclineButtonClicked

### AcceptButtonClicked

SfPopupLayout.PopupView.AcceptButtonClicked will be fired when the accept button in the footer is clicked. 

Derive a class from `ICommand` and implement the neccessary interface. Return true in the `CanExecute()` method to close the popup and return false to prevent popup from closing.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.AcceptCommand = new AcceptButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Accept Button Event handler

public class AcceptButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
       
    }
}
{% endhighlight %}

### DeclineButtonClicked

[SfPopupLayout.PopupView.DeclineButtonClicked](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~DeclineCommand.html) will be fired when the decline button in the footer is clicked.  

Derive a class from `ICommand` and implement the neccessary interface. Return true in the `CanExecute()` method to close the popup and return false to prevent popup from closing.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.DeclineCommand = new DeclineButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Decline Button Event handler

public class DeclineButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
       
    }
}
{% endhighlight %}