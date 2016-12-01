---
layout: post
title:  Getting Started for Essential Xamarin.Android PDF viewer
description: getting started
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Getting Started

This section explains about the assemblies required for the deployment of SfPdfViewer and how to create simple application using the SfPdfViewer control.

## Assembly Required

### Android project

android\Syncfusion.SfPdfViewer.Android.dll

## Create a simple application with the SfPdfViewer

Follow the below steps to create a simple application with the SfPdfViewer and load a PDF document.

* Create a new blank application for Xamarin.Android in the Visual Studio and refer the required assembly to the project. 

Add the following Xml code in you Main.axml to make use of SfPdfViewer.
   
{% tabs %}
{% highlight xaml %}

   <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:focusable="true"
    android:focusableInTouchMode="true"
    android:id="@+id/parentview">
	    <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
    </LinearLayout>

{% endhighlight %}
{% endtabs %}

## Loading PDF document

The LoadDocument method can be used to load a PDF document using stream input.

{% tabs %}   
{% highlight c# %}

     protected override void OnCreate(Bundle bundle)
       {
           base.OnCreate(bundle);		
           SetContentView(Resource.Layout.Main);
		   SfPdfViewer pdfViewerControl = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
           Stream docStream = Assets.Open("GIS Succinctly.pdf");
           pdfViewerControl.LoadDocument(docStream);		   
       }

{% endhighlight %}
{% endtabs %}


## Unloading PDF document from the PDF viewer

The SfPdfViewer control allows you to unload the PDF document from the viewer when the control is not in use anymore. This releases the PDF document and all its associated resources.

We need to call the Unload method of SfPdfViewer control as in the below code snippet to achieve the same.

{% tabs %} 
{% highlight c# %}

pdfViewerControl.Unload();

{% endhighlight %}
{% endtabs %}

This is how the final output will look like on Android devices.

![](pdfviewer_images/gettingstarted.png)