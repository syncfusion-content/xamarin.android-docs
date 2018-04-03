---
layout: post
title: Popup Animations | SfPopupLayout |Xamarin.Android | Syncfusion
description: Animations in SfPopupLayout
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Popup Animations

Built-in animations are available in SfPopupLayout, which is applied when the PopupView opens and closes in the screen.
SfPopupLayout has different animation modes as listed below.

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[Zoom](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Zoom-out animation will be applied if the PopupView opens and zoom-in animation will be applied if the PopupView closes. This is the default AnimationMode</td>
</tr>
<tr>
<td> {{'[Fade](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes</td>
</tr>
<tr>
<td> {{'[SlideOnLeft](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[SlideOnTop](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[None](https://help.syncfusion.com/cr/cref_files/xamarin-android/sfpopuplayout/Syncfusion.SfPopupLayout.Android~Syncfusion.Android.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Animation will not be applied.</td>
</tr>
</table>

N> Setting of AnimationMode is same for both `Displaying pop-up when the SfPopupLayout is set as root view`and `Displaying pop-up when the SfPopupLayout is not set as root view` 

## Zoom 

Zoom-out animation will be applied if the PopupView opens and Zoom-in animation will be applied if the PopupView closes.

{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.Zoom;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in Android device respectively.

![](GettingStarted_images/ZoomAnimation.gif)

## Fade 

Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes

{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.Fade;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in Android device respectively.

![](GettingStarted_images/FadeAnimation.gif)

## SlideOnLeft 

PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.

{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnLeft;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in Android device respectively.

![](GettingStarted_images/SlideOnLeftAnimation.gif)

## SlideOnTop 

PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.

{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnTop;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in Android device respectively.

![](GettingStarted_images/SlideOnTopAnimation.gif)

## None

Animation will not be applied.

{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.None;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}

Executing the above codes renders the following output in Android device respectively.

![](GettingStarted_images/AnimationMode_None.gif)