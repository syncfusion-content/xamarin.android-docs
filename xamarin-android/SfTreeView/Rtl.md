---
layout: post
title: RTL | TreeView for Xamarin.Android | Syncfusion
description: Describes how to enable right-to-left localization treeview.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Right-to-left localization.

 TreeView supports right-to-left localization by setting the [LayoutDirection](https://developer.xamarin.com/api/type/Android.Views.LayoutDirection/) of root layout to [LayoutDirection.Rtl](https://developer.xamarin.com/api/field/Android.Views.LayoutDirection.Rtl/) or changing device's layout direction by enabling `Force RTL layout direction` in `Settings > Developer Options`.


## Application setup to support RTL.

In `AndroidManifest.xml` file, `<uses-sdk>` node sets the `android:minSdkVersion` attribute to `API 17 or higher on Android`, and the `<application>` node sets the `android:supportsRtl` attribute to `true` to your application to respond for right-to-left localizaton.

{% tabs %}
{% highlight xml %}

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android" android:versionCode="1" android:versionName="1.0" package="com.companyname.RTLTreeView">
    <uses-sdk android:minSdkVersion="17" />
    <application android:label="RTLTreeView.Android" android:supportsRtl="true"></application>
</manifest>

{% endhighlight %}
{% endtabs %}

N> If you need to override the content view of `TreeView` with your custom view, need to layout views in application based on `LayoutDirection` to respond for right-to-left localization.

For more information regarding right-to-left localization you can refer [this](https://developer.android.com/training/basics/supporting-devices/languages#MirroringAddResources) link.

## Device setup to support RTL

Right-to-left localization can then be tested by changing the device/emulator to use the right-to-left language, or by enabling `Force RTL layout direction` in `Settings > Developer Options`.

N> If your application targets Android `API level 16` or lower, the `android:supportsRtl` attribute is ignored, along with any `start` and `end` attribute values that appear in your applications layout files. In this case, RTL layout mirroring doesn't happen automatically in your application.