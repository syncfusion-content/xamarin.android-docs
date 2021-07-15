---
layout: post
title: Data Labels
description: This section describes about data labels.
platform: Xamarin.Android
control: SfMaps
documentation: ug
---

# Data Labels

Data labels are used to display the values of shapes.

## Adding data labels

 The [`ShowItems`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.ShapeFileLayer.html#Com_Syncfusion_Maps_ShapeFileLayer_ShowItems) property, which is a boolean property, displays or hides the data labels in shapes. Set the [`ShapeValuePath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.ShapeSetting.html#Com_Syncfusion_Maps_ShapeSetting_ShapeValuePath) property to get the data labels bound to each shape.

{% tabs %}

{% highlight c# %}

            SfMaps maps = new SfMaps(this);
         
            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowItems = true;

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            layer.DataSource = GetDataSource();

            layer.ShapeIdPath = "Name";

            layer.ShapeIdTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Type";

            maps.Layers.Add(layer);

            SetContentView(maps);

{% endhighlight %}

{% endtabs %}

You can use below collection as a datasource of SfMaps.

{% tabs %}

{% highlight c# %}

        JSONArray GetDataSource()
        {
            JSONArray array = new JSONArray();

            array.Put(getJsonObject("Alabama", "Vegetables", 49));
            array.Put(getJsonObject("Alaska", "Vegetables", 43));
            array.Put(getJsonObject("Arizona", "Rice", 31));
            array.Put(getJsonObject("Arkansas", "Vegetables", 36));
            array.Put(getJsonObject("California", "Rice", 50));
            array.Put(getJsonObject("Colorado", "Rice", 49));
            array.Put(getJsonObject("Connecticut", "Grains", 7));
            array.Put(getJsonObject("Delaware", "Grains", 3));
            array.Put(getJsonObject("Florida", "Rice", 29));
            array.Put(getJsonObject("Georgia", "Rice", 36));
            array.Put(getJsonObject("Hawaii", "Grains", 4));
            array.Put(getJsonObject("Idaho", "Grains", 4));
            array.Put(getJsonObject("Illinois", "Vegetables", 20));
            array.Put(getJsonObject("Indiana", "Grains", 11));
            array.Put(getJsonObject("Iowa", "Vegetables", 6));
            array.Put(getJsonObject("Kansas", "Rice", 6));
            array.Put(getJsonObject("Kentucky", "Grains", 8));
            array.Put(getJsonObject("Louisiana", "Rice", 48));
            array.Put(getJsonObject("Maine", "Grains", 4));
            array.Put(getJsonObject("Maryland", "Grains", 10));
            array.Put(getJsonObject("Massachusetts", "Grains", 11));
            array.Put(getJsonObject("Michigan", "Grains", 16));
            array.Put(getJsonObject("Minnesota", "Wheat", 10));
            array.Put(getJsonObject("Mississippi", "Vegetables", 36));
            array.Put(getJsonObject("Missouri", "Vegetables", 30));
            array.Put(getJsonObject("Montana", "Grains", 3));
            array.Put(getJsonObject("Nebraska", "Rice", 5));
            array.Put(getJsonObject("Nevada", "Wheat", 6));
            array.Put(getJsonObject("New Hampshire", "Grains", 34));
            array.Put(getJsonObject("New Jersey", "Vegetables", 14));
            array.Put(getJsonObject("New Mexico", "Rice", 35));
            array.Put(getJsonObject("New York", "Vegetables", 24));
            array.Put(getJsonObject("North Carolina", "Rice", 45));
            array.Put(getJsonObject("North Dakota", "Grains", 3));
            array.Put(getJsonObject("Ohio", "Vegetables", 18));
            array.Put(getJsonObject("Oklahoma", "Rice", 47));
            array.Put(getJsonObject("Oregon", "Wheat", 7));
            array.Put(getJsonObject("Pennsylvania", "Vegetables", 20));
            array.Put(getJsonObject("Rhode Island", "Grains", 4));
            array.Put(getJsonObject("South Carolina", "Rice", 49));
            array.Put(getJsonObject("South Dakota", "Grains", 3));
            array.Put(getJsonObject("Tennessee", "Vegetables", 41));
            array.Put(getJsonObject("Texas", "Vegetables", 38));
            array.Put(getJsonObject("Utah", "Rice", 6));
            array.Put(getJsonObject("Vermont", "Grains", 3));
            array.Put(getJsonObject("Virginia", "Rice", 13));
            array.Put(getJsonObject("Washington", "Vegetables", 12));
            array.Put(getJsonObject("West Virginia", "Grains", 5));
            array.Put(getJsonObject("Wisconsin", "Grains", 10));
            array.Put(getJsonObject("Wyoming", "Wheat", 3));
            return array;
        }
        JSONObject getJsonObject(String name, String type, double count)
        {
            JSONObject obj = new JSONObject();
            obj.Put("Name", name);
            obj.Put("Type", type);
            obj.Put("Count", count);
            return obj;
        }
{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel_img.png)

## Setting contrast color

Based on the background color of the shapes, contrast color will be applied to data labels.

{% tabs %}

{% highlight c# %}

            SfMaps maps = new SfMaps(this);

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowItems = true;

            layer.DataSource = GetDataSource();

            layer.ShapeIdPath = "Name";

            layer.ShapeIdTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Name";

            layer.ShapeSettings.ShapeColorValuePath = "Count";

            RangeColorMapping rangeColorMapping = new RangeColorMapping();

            rangeColorMapping.From = 0;

            rangeColorMapping.To = 25;

            rangeColorMapping.Color = Color.ParseColor("#FFD84F");

            RangeColorMapping rangeColorMapping1 = new RangeColorMapping();

            rangeColorMapping1.From = 25;

            rangeColorMapping1.To = 50;

            rangeColorMapping1.Color = Color.ParseColor("#316DB5");

            layer.ShapeSettings.ColorMapping.Add(rangeColorMapping);

            layer.ShapeSettings.ColorMapping.Add(rangeColorMapping1);

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.SmartLabelMode = IntersectAction.Trim;

            layer.DataLabelSettings = dataLabelSetting;

            maps.Layers.Add(layer);

            SetContentView(maps);
			
{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel_contrast_color.png)

## Customizing data labels

Data labels can be customized using the [`DataLabelSetting`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.ShapeFileLayer.html#Com_Syncfusion_Maps_ShapeFileLayer_DataLabelSettings) property in shape file layer. The typeface, color, and text size can be customized using the [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_Typeface), [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_TextColor), and [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_TextSize) properties.

{% tabs %}

{% highlight c# %}

             SfMaps maps = new SfMaps(this);
         
            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowItems = true;

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            layer.DataSource = GetDataSource();

            layer.ShapeIdPath = "Name";

            layer.ShapeIdTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Type";

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.TextColor = Color.Blue;

            dataLabelSetting.Typeface = Typeface.Create("cursive", TypefaceStyle.Italic);

            dataLabelSetting.TextSize = 12;

            layer.DataLabelSettings = dataLabelSetting;

            maps.Layers.Add(layer);

            SetContentView(maps);

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel_customization.png)

## To smartly align data labels

The [`SmartLabelMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_SmartLabelMode) property aligns the labels smartly within shape boundaries and avoids labels overlapping. Labels can be customized using the `Hide`, `Trim`, and `None` options.

{% tabs %}

{% highlight c# %}

            SfMaps maps = new SfMaps(this);
         
            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowItems = true;

            layer.DataSource = GetDataSource();

            layer.ShapeIdPath = "Name";

            layer.ShapeIdTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Name";

            layer.ShapeSettings.ShapeColorValuePath = "Count";

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.SmartLabelMode = IntersectAction.Trim;

            layer.DataLabelSettings = dataLabelSetting;

            maps.Layers.Add(layer);

            SetContentView(maps);

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel_smartlabelmode_trim.png)

## To avoid overlap in data labels

The [`IntersectionAction`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_IntersectionAction) property aligns labels that overlap. Labels can be customized using the `Hide`, `Trim`, and `None` options. First, set the [`SmartLabelMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.DataLabelSetting.html#Com_Syncfusion_Maps_DataLabelSetting_SmartLabelMode) property to `None`.

{% tabs %}

{% highlight c# %}

            SfMaps maps = new SfMaps(this);
         
            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowItems = true;

            layer.DataSource = GetDataSource();

            layer.ShapeIdPath = "Name";

            layer.ShapeIdTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Name";

            layer.ShapeSettings.ShapeColorValuePath = "Count";

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.IntersectionAction = IntersectAction.Hide;

            dataLabelSetting.SmartLabelMode = IntersectAction.None;

            layer.DataLabelSettings = dataLabelSetting;

            maps.Layers.Add(layer);

            SetContentView(maps);

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel_intersection_action_hide.png)   
