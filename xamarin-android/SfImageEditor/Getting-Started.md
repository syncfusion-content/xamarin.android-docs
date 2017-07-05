---
layout: post
title: Getting Started for Essential Xamarin.Android ImageEditor
description: getting started
platform: Xamarin.Android
control: SfImageEditor
documentation: ug
---
# Getting Started

This section explains you the steps required to load an image to the image editor. Image editor has a built in toolbar which has options to edit the image with shapes, path, text, crop and flip.

## Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio\15.2.0.40\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfImageEditor.Andriod.dll

# Add and configure the image editor

The following steps explain on how to create a image editor  and configure its elements,

* Create an instance of SfImageEditor.

{% highlight C# %}

    SfImageEditor editor  = new SfImageEditor(this);
    SetContentView(editor);

{% endhighlight %}

* Load an image to the image editor as bitmap object.Since SfImageEditor supports bitmap images you can load the image to the control as a bitmap object only.

{% highlight C# %}

    SfImageEditor editor = new SfImageEditor();
    editor.Bitmap = */ Your Bitmap */

{% endhighlight %}



* Loading the image to the SfImageEditor, you can start to edit the image by using the built-in Toolbars.

![SfImageEditor](ImageEditor_images/gettingstarted.png)

