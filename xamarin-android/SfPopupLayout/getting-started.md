---
layout: post
title: Getting Started | SfPopupLayout |Xamarin.Android | Syncfusion
description: Getting Started with SfPopupLayout
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Getting Started

This section provides a quick overview for working with SfPopupLayout in Xamarin.Android. Walk through the entire process of creating a simple application with this control.

## Assembly deployment

After installing Essential Studio for Xamarin, all the required assemblies can be found in {Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib this installation folders.

e.g., C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.

### SfPopupLayout for Xamarin.Android

The following assembly should be added as reference from the "lib" folder to use SfPopupLayout in the application.

<table>
<tr>
<th> Project </th>
<th> Required assemblies </th>
</tr>
<tr>
<td> Xamarin.Android </td>
<td> android\Syncfusion.SfPopupLayout.Android.dll </td>
</tr>
</table>

## NuGet Configuration

To install SfPopupLayout control in the application, configure the NuGet package of the Syncfusion components. Refer to the following KB to configure the NuGet package of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be added to use SfPopupLayout control in the application:

<table>
<tr>
<th> Project </th>
<th> Required packages </th>
</tr>
<tr>
<td> Xamarin.Android </td>
<td> Syncfusion.Xamarin.SfPopupLayout.Android </td>
</tr>
</table>

Refer to the following screenshot in which the Syncfusion.Xamarin.SfPopupLayout.Android package is highlighted:

![](GettingStarted_images/NuGetInstall.png)

## Create a simple popup

SfPopupLayout control can be configured entirely in C# code. To create a sample application for this control, follow the topics: 

In this walk through, you will create a new application with SfPopupLayout.

* [Creating the project](#creating-the-project)  
* [Adding SfPopupLayout in Xamarin.Android](#adding-sfpopuplayout-in-xamarin.android) 
* [Adding a TextView as the ContentView of the SfPopupLayout](#adding-a-textview-as-the-contentview-of-the-sfpopuplayout) 
* [AppearanceMode](#appearancemode) 
* [Showing SfPopupLayout at various position](#showing-sfPopupLayout-at-various-position)
* [AnimationMode](#animationmode)
* [Sample Link](#sample-link)

### Creating the project

Create a new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

### Adding SfPopupLayout in Xamarin.Android

1. Add the required assembly references to the project as mentioned in the [Assembly deployment](#assembly-deployment) section or install the NuGet as mentioned in the [NuGet Configuration](#nuget-configuration) section.

2. Import SfPopupLayout control under the namespace `Syncfusion.Android.PopupLayout`.

3. The SfPopupLayout can be displayed by the following methods. 
    
    * The SfPopupLayout can be displayed by making it as the base view or content view of the activity. We will refer this approach as Type A throughout this page.

    * You can continue to keep your view as the content view of the activity and still display popup over your view by simply calling the SfPopupLayout.Show() method. We will refer this approach as Type B throughout this page.

4. For Type A, set the view over which the SfPopupLayout should be displayed as the content of the SfPopupLayout using [SfPopupLayout.Content](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Content.html) property.

5. Create an instance of SfPopupLayout control and set it as ContentView of that Activity. Refer to the following code example to add this control to the application:

#### Type A:

{% highlight c# %}

using Syncfusion.Android.PopupLayout;

namespace GettingStarted
{
    public class MainActivity : Activity 
    {
       SfPopupLayout popupLayout;
       Button showPopupButton;
       LinearLayout mainLayout;

        protected override void OnCreate (Bundle bundle) 
        {
            base.OnCreate (bundle); 
            mainLayout = new LinearLayout(this);
            mainLayout.Orientation = Orientation.Vertical;
            mainLayout.SetBackgroundColor(Color.White);

            showPopupButton = new Button(this);
            showPopupButton.Click += ShowPopupButton_Click;
            showPopupButton.SetTextColor(Color.White);
            showPopupButton.Text = "Click to show Popup";

            mainLayout.AddView(showPopupButton, ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.WrapContent);
            popupLayout = new SfPopupLayout(this);
            popupLayout.Content = mainLayout;

            SetContentView(popupLayout);
        } 

        private void ShowPopupButton_Click(object sender, System.EventArgs e)
        {
            popupLayout.Show();
        }
    } 
}

{% endhighlight %}

#### Type B:

{% highlight c# %}

using Syncfusion.Android.PopupLayout;

namespace GettingStarted
{
    public class MainActivity : Activity 
    {
       SfPopupLayout popupLayout;
       Button showPopupButton;
       LinearLayout mainLayout;

        protected override void OnCreate (Bundle bundle) 
        {
            base.OnCreate (bundle); 
            mainLayout = new LinearLayout(this);
            mainLayout.Orientation = Orientation.Vertical;
            mainLayout.SetBackgroundColor(Color.White);

            showPopupButton = new Button(this);
            showPopupButton.Click += ShowPopupButton_Click;
            showPopupButton.SetTextColor(Color.White);
            showPopupButton.Text = "Click to show Popup";

            mainLayout.AddView(showPopupButton, ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.WrapContent);
            popupLayout = new SfPopupLayout(this);
            SetContentView(mainLayout);
        } 

        private void ShowPopupButton_Click(object sender, System.EventArgs e)
        {
            popupLayout.Show(mainLayout);
        }
    } 
}

{% endhighlight %}

If we run the above sample, the below output will appears on Android device as shown below.
![](GettingStarted_images/DefaultAppearance.png)

### Customizing Positioning

SfPopupLayout allows you to show the Popup content at various position based on the requirement.

Following are the list of options available to position the SfPopupLayout in your desired position

* [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~IsOpen.html) property - Shows SfPopupLayout at the center.
* [SfPopupLayout.Show()](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Show.html) - It is similar to SfPopupLayout.IsOpen property.
* [SfPopupLayout.Show(x-position, y-position)](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~Show.html) - Shows SfPopupLayout at the specified X and y position.
* [SfPopupLayout.ShowAtTouchPoint()](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~ShowAtTouchPoint.html) - Shows SfPopupLayout at the touch point.
* [SfPopupLayout.ShowRelativeToView(View, RelativePosition)](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.SfPopupLayout~ShowRelativeToView.html) - Choose to show SfPopupLayout at any of the 8 positions relative to the specified view.

### Customizing Layouts

By default, you can choose from the following layouts available in SfPopupLayout using the property [SfPopupLayout.AppearanceMode](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AppearanceMode.html).

* [OneButton](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AppearanceMode.html) - Shows SfPopupLayout with OneButton in the FooterView. This is the default value.
* [TwoButton](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AppearanceMode.html) - Shows SfPopupLayout with TwoButtons in the FooterView.
* You can also customize the entire view of the popup by loading templates or custom views individually for the header, body and footer of the popup.

#### Adding a TextView as the ContentView of the SfPopupLayout

Any view can be added as the popup content using the [SfPopupLayout.PopupView.ContentView](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.PopupView~ContentView.html) property to refresh it.

Refer to the following code example in which a text view is added as popup content:

{% highlight c# %}}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....

	 TextView popupContentView = new TextView(this) { Text = "This is the Customized view for SfPopupLayout" };
     popupContentView.SetTextColor(Color.Black);
     popupContentView.SetBackgroundColor(Color.LightSkyBlue);
      
     // Adding ContentView of the SfPopupLayout
     popupLayout.PopupView.ContentView = popupContentView;
	....
}

{% endhighlight %}

N> Setting of ContentView is same for both Type A and Type B

If we run the above sample, the below output will appears on Android device as shown below.
![]GettingStarted_images/ContentView.png)

### Customizing Animations

Built-in animations are available in SfPopupLayout, which is applied when the PopupView opens and closes in the screen.
By default, you can choose from the following Animations available in SfPopupLayout using the property [SfPopupLayout.AnimationMode](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html).

* [Zoom](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html) - Zoom-out animation will be applied if the PopupView opens and zoom-in animation will be applied if the PopupView closes. This is the default AnimationMode
* [Fade](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html) - Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes.
* [SlideOnLeft](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html) - PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.
* [SlideOnTop](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html) - PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.
* [None](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html) - Animation will not be applied.

### Sample link

You can download the source code of this sample [here]().
