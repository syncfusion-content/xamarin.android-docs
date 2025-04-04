---
layout: post
title: Custom view of Syncfusion<sup>&reg;</sup> SfImageEditor control in Xamarin.Android
description: Learn how to add and customize the custom view with its settings in Syncfusion<sup>&reg;</sup> ImageEditor for Xamarin.Android
platform: xamarin.android
control: ImageEditor
documentation: ug
---

# CustomView and its customization

You can add any custom shapes or views to an image using the `AddCustomView` method in the image editor control. To add a custom view, specify the view and its desired `CustomViewSettings` as shown in the following code snippet.

{% highlight C# %}

            ImageView customView = new ImageView(this);
            customView.LayoutParameters = new Android.Views.ViewGroup.LayoutParams(200, 200);
            customView.SetImageResource(Resource.Drawable.sample);
            imageEditor.AddCustomView(customView, new CustomViewSettings());

{% endhighlight %}

## CustomViewSettings

CustomViewSettings is defined to set the values for `CanMaintainAspectRatio`, `Bounds` and `Angle`.

• CanMaintainAspectRatio property is used to set the Boolean value to maintain the aspect ratio value or not when resizing the custom view.

•  Bounds property is used to set the bounds of the custom view. Using this property, you can position the custom view wherever you want on the image. In percentage, the value should fall between 0 and 100.

• Angle property is used to set the angle of the custom view. Using this property, you can rotate the custom view at desired angle.

* [`EnableDrag`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.CustomViewSettings.html#Syncfusion_SfImageEditor_Android_CustomViewSettings_EnableDrag) - Controls the dragging of selected view over the image.

{% capture codesnippet1 %}

{% highlight C# %}

            CustomViewSettings customViewSettings = new CustomViewSettings()
            {
                CanMaintainAspectRatio = false,
                Bounds = new Rectangle(0, 0, 100, 100),
                Angle = 45
            };

{% endhighlight %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

![SfImageEditor](ImageEditor_images/CustomView.png)

## CustomView Rotation

You can rotate and resize the custom view by enabling the `RotatableElements` property of image editor. `ImageEditorElements` is an enum type with values Text, CustomView and None as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

        imageEditor.RotatableElements = ImageEditorElements.CustomView;   

{% endhighlight %}

{% endtabs %}

N> The default value for RotatableElements is `None`.

You can rotate the custom view based on a particular angle using `Angle` property in `CustomViewSettings` as shown in the following code snippet. 

{% tabs %}

{% highlight C# %}

        imageEditor.AddCustomView(customImage, new CustomViewSettings(){Angle = 45});    

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/rotation.png)