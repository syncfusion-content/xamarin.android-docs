---
layout: post
title:  Getting Started for Essential Xamarin.Android PDF viewer
description: getting started
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Getting started

This section demonstrates how to create an application that displays a PDF file using SfPdfViewer control.

## Assemblies Required

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{Essential Studio version}\Xamarin\lib\android\

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\15.3.0.28\Xamarin\lib\android\

For creating a PDF Viewer for android, the following assemblies need to be referenced in your Android project.

* Syncfusion.Compression.Portable
* Syncfusion.Pdf.Portable
* Syncfusion.SfPdfViewer.Android

## Create a simple PDF Viewer

Create a new blank application for Android using Visual Studio and name it as “GettingStartedDroid”. Refer the above-mentioned assemblies to the project. 

Add a PDF document you need to display in the PDF Viewer (here GIS Succinctly.pdf is used) and set the build action property as “AndroidAssest”.

Add the below code in the Main.axml to include PDF Viewer control.
   
{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

Please add the below code snippet in the MainActivity class

* In the MainActivity.cs class, declare an instance of SfPdfViewer globally. 
* In the override method OnCreate, set the content view to Main, locate the PDF viewer and load the PDF document.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    Stream PdfStream = Assets.Open("GIS Succinctly.pdf");
    pdfViewer.LoadDocument(PdfStream);
}

{% endhighlight %}
{% endtabs %}

Deploying this project in the Android device would display the PDF document and allow you to scroll and zoom through the pages.

## Unloading PDF document from the Viewer

The SfPdfViewer control allows you to unload the PDF document from the viewer, when the PDF document is not in use anymore. This releases the PDF document and all its associated resources of the application.

You need to call the Unload method of SfPdfViewer control as in the below code snippet to achieve the same.

{% tabs %}   
{% highlight c# %}

pdfViewerControl.Unload();

{% endhighlight %}
{% endtabs %}

## How to get & set the current page number?

PageChanged event of the PDF viewer can be used to track the change in the current page being displayed in the PDF viewer. 

This below code snippet demonstrates how to track the current page number being viewed using PageChanged event and how to navigate to the respective page in the PDF Viewer.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="1"
            android:layout_height="50dp">
    <EditText
          android:id="@+id/pagenumberentry"
          android:layout_width="50dp"
          android:layout_height="30dp"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:textAlignment="center"
          android:background="@drawable/edittextbg"
          android:textColor="@android:color/black"
          android:inputType="number"
          android:selectAllOnFocus="true"
          android:gravity="center" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

EditText pageNumberEntry;
SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    
    //Access the controls in the design.
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    pageNumberEntry = FindViewById<EditText>(Resource.Id.pagenumberentry);

    //Wireup PageChanged event with PdfViewer_PageChanged
    pdfViewer.PageChanged += PdfViewer_PageChanged;
    //Wireup KeyPress event with PageNumberEntry_KeyPress
    pageNumberEntry.KeyPress += PageNumberEntry_KeyPress;
}

private void PdfViewer_PageChanged(object sender, PageChangedEventArgs args)
{
    //Set the text of PageNumerEntry EditText control to the PageNumber event argument of PageChanged event.
    pageNumberEntry.Text = args.PageNumber.ToString();
}

private void PageNumberEntry_KeyPress(object sender, Android.Views.View.KeyEventArgs e)
{
    e.Handled = false;
    if (e.Event.Action == KeyEventActions.Down && e.KeyCode == Keycode.Enter)
    {
        int pageNumber = 0;
        //Validated the entered text input is interger or validate.
        if (int.TryParse((pageNumberEntry.Text), out pageNumber))
        {
            if ((pageNumber > 0) && (pageNumber <= pdfViewer.PageCount))
                pdfViewer.GoToPage(pageNumber);
        }
         pageNumberEntry.ClearFocus();
        InputMethodManager inputMethodManager = (InputMethodManager)mainView.Context.GetSystemService(Context.InputMethodService);
        inputMethodManager.HideSoftInputFromWindow(mainView.WindowToken, HideSoftInputFlags.None);
    }
}

{% endhighlight %}
{% endtabs %}

N>**When a page number which is not in the bounds (1 – page count) is provided as an input to the GoToPage method, no action will be performed.

## How to get the total page number?

PageCount property of the PDF viewer can be used to acquire the total number of pages in the PDF document that is being loaded. The PageCount property of the PDF viewer will be updated only after loading the PDF document, it can be tracked using DocumentLoaded event of the PDF viewer.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="1"
            android:layout_height="50dp">
    <TextView
          android:id="@+id/pagecounttext"
          android:layout_width="50dp"
          android:textAlignment="center"
          android:textColor="@android:color/black"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:textSize="18dp"
          android:gravity="center"
          android:text="0" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

TextView pageCountText;
SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    
    //Access the controls in the design.
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    pageCountText = FindViewById<TextView>(Resource.Id.pagecounttext);

    //Wireup DocumentLoaded event with PdfViewer_DocumentLoaded
    pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
}

private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
{
    //Set the text of the PageCountText TextView to PageCount of PDF viewer
    pageCountText.Text = pdfViewer.PageCount.ToString();
}

{% endhighlight %}
{% endtabs %}