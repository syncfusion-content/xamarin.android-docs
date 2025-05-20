---
layout: post
title: Register a license key in Xamain.Android application | Syncfusion
description: Learn here about how to register Syncfusion® Xamarin.Android license key for Xamarin.Android application for license validation.
platform: xamarin.android
control: Essential Studio<sup>®</sup>
documentation: ug
---


# Register Syncfusion<sup>®</sup> License key in Xamarin.Android application

The generated license key is just a string that needs to be registered before any Syncfusion<sup>®</sup> control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.
* Syncfusion<sup>®</sup> license validation is done offline during application execution and does not require internet access.  Apps registered with a Syncfusion<sup>®</sup> license key can be deployed on any system that does not have an internet connection.

### Xamarin.Android

You can register the license key in **OnCreate** override method of your main activity class before initializing any Syncfusion<sup>®</sup> control.

{% tabs %}
{% highlight c# %}
protected override void OnCreate(Bundle savedInstanceState)
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	base.OnCreate(savedInstanceState);

	// Set our view from the "main" layout resource
	SetContentView(Resource.Layout.Main);
}
{% endhighlight %}
{% endtabs %}
