---
layout : post
title : ToolbarCustomization in Syncfusion SfImageEditor control in Xamarin.Android
description : Learn how to customize toolbar in ImageEditor for Xamarin.Android
platform : xamarin.android
control : ImageEditor
documentation : ug
---

# ToolbarCustomization

You can customize color palette, toolbar visibility and appearance of each toolbar item.

## Customize toolbar items

SfImageEditor control supports to customize and configure the appearance of toolbar menu. You can customize image editor toolbar by adding respective FooterToolbarItem and HeaderToolbarItem 

#### ToolbarItem

You can customize each toolbar item with the help of `Text` and `Icon` properties.

##### Name
 
 You can get or set the name of individual built-in and dynamically added toolbar item with the help of `Name` property. 

{% highlight C# %}

        	protected override void OnCreate(Bundle bundle)
            {			
                InitializeComponent();
                SfImageEditor editor = new SfImageEditor();
                var itemName = editor.ToolbarSettings.ToolbarItems[2].Name;
            }

{% endhighlight %}

N> The list of available built-in toolbar item names are "back,Text,Add,TextColor,FontFamily,Arial,Noteworthy,Marker Felt,Bradley Hand,SignPainter,Opacity,Path,StrokeThickness,Colors,Opacity,Shape,Rectangle,StrokeThickness,Circle,Arrow,Transform,Crop,free,original,square,3:1,3:2,4:3,5:4,16:9,Rotate,Flip,Reset,Undo,Redo,Save"

N> We can't modify the name of existing built-in toolbar item and also can't create toolbar item with these list

ImageEditor Toolbar menu contains set of header and footer menu items which helps to perform image editor actions and this can be categorized into the following types,

1.HeaderToolbarItem
2.FooterToolbarItem
3.SubItems

### Adding HeaderToolbarItem

`HeaderToolbarItem` will be arranged on top of the image editor and you can customize header toolbar item with the help of Icon and Text as like below,

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new HeaderToolbarItem() { Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.share), Text = "Share" });

{% endhighlight %}

### Adding FooterToolbarItem   

 `FooterToolbarItem` will be arranged on bottom of the image editor and you can customize footer toolbar item with the help of Icon and Text along with sub items.

Refer to the below code snippet to customize footer toolbar item,

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.delete), Text="Delete" });
            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.more), Text="More" });

{% endhighlight %}

### Adding SubItems to the FooterToolbarItem

`SubItems` only applicable for `FooterToolbarItem` and it represents grouped action of respective footer toolbar item. SubItems will be arranged above the footer toolbar item layout and you can also customize sub items appearance as like main toolbar items. 

Refer to the below code snippet to customize sub items of footer toolbar item,

{% highlight C# %}

 	 editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
            {
                Text = "More",
                Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.more),
                SubItems = new ObservableCollection<ToolbarItem>()
                {
                   new ToolbarItem() {
                Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.download)
                },
                   new ToolbarItem() {
                Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.share)
                } }
            });

{% endhighlight %}

N> You can remove existing toolbar items(Text,Path,Shape,Transform,Reset,Undo,Redo and Save) from the image editor toolbarItems collection based on the index value. 

You can change icon and text value dynamically for any of already added toolbar item based on the index as like below,

{% highlight C# %}

editor.ToolbarSettings.ToolbarItems[5].Text = "new item";
editor.ToolbarSettings.ToolbarItems[3].Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.Image)

{% endhighlight %}


### ToolbarItemSelected event 

Whenever you tap the toolbar menu item, the `ToolbarItemSelected` event will be triggered and you can get the respective tapped toolbar item as an argument as shown below, 

{% highlight C# %}

        protected override void OnCreate(Bundle bundle)
        {
			   . . .

            editor.ToolbarSettings.ToolbarItemSelected += ToolbarSettings_ToolbarItemSelected;

			   . . .
        }

        private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
        {
            Toast.MakeText(ApplicationContext, "Selected ToolbarItem is  " + e.ToolbarItem.Text, ToastLength.Long).Show();
        }

{% endhighlight %}

#### MoveSubItemsToFooterToolbar 

`MoveSubItemsToFooterToolbar` boolean property of ToolbarItemSelected event argument decides the placement of each sub items of respective footer toolbar item. 

If you set the value to `true`, the respective sub items of footer item will be placed on footer toolbar layout. If you set `false`, then the sub items will be placed above the footer toolbar layout.

{% highlight C# %}

        protected override void OnCreate(Bundle bundle)
            {
                        . . .

               
            SfImageEditor edit = new SfImageEditor(this);
            edit.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
				{
					Text = "NewFooterItem",
					SubItems = new System.Collections.Generic.List<ToolbarItem>()
							{
								new ToolbarItem(){ Text= "Subitem1"},
								new ToolbarItem(){ Text= "Subitem2"},
								new ToolbarItem(){ Text= "Subitem3"},
							}
				});
                edit.ToolbarSettings.ToolbarItemSelected += ToolbarSettings_ToolbarItemSelected;
                        
                        . . .
            }


          private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
            {
                if(e.ToolbarItem != null && e.ToolbarItem is FooterToolbarItem)
                {
                    if(e.ToolbarItem.Text == "NewFooterItem")
                    {
                        e.MoveSubItemsToFooterToolbar = false;
                    }
                }
            }

{% endhighlight %}

N> This is not applicable for built-in footer toolbar items .


## To Hide/Show toolbar
 
 To show or hide toolbar by setting toolbar IsVisible property to either true or false. By default toolbar IsVisible property is set to true.

{% tabs %}

{% highlight C# %}

     
     editor.ToolbarSettings.IsVisible = false;
     

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/toolbarvisibility.png)

## To Hide/Visible the toolbar Item

You can hide or show the toolbar items by specifying its icon name and set boolean value to false or true.

N> You can customize icon by specifying its names like text, path, shapes, transform, rectangle, circle, arrow, flip, crop, rotate, reset, undo, Redo and save.


{% tabs %}

{% highlight C# %}

    editor.SetToolbarItemVisibility("text,save", false);

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/toolbaritemvisibility.png)


## To customize the ColorPalette

You can change default colors of the ColorPalette in toolbar.

{% tabs %}

{% highlight C# %}

    	ObservableCollection<Color> CustomColorPalette = new ObservableCollection<Color>()
	{
				Color.Yellow,
				Color.Blue,
				Color.DarkGray
	};

			editor.ColorPalette = CustomColorPalette;
{% endhighlight %}

{% endtabs %}

## ToolbarHeight Customization

You can customize `height of the toolbar` and also toolbar items `icon` and `text`.

### Customize Toolbar Height 

SfImageEditor control supports to customize the default height of `Header`, `Footer` and `Sub item` Toolbar by using following properties,
1.	HeaderToolbarHeight
2.	FooterToolbarHeight 
3.	SubItemToolbarHeight

Toolbar items will be resize based on the toolbar height. To change Height of the Toolbar as like below,

{% tabs %}

{% highlight C# %}

    editor.ToolbarSettings.HeaderToolbarHeight = 70;
    editor.ToolbarSettings.FooterToolbarHeight = 70;
    editor.ToolbarSettings.SubItemToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/ToolbarHeight.png)

### Individual Toolbar Item Height Customization

To arrange toolbar items aspect fit based on the toolbar height by using following properties  

1.  TextHeight
2.  IconHeight

To change the toolbar item Text and Icon height as like below,

{% tabs %}

{% highlight C# %}

     FooterToolbarItem footerItem = new FooterToolbarItem()
            {
                IconHeight=40,
                TextHeight=20,
                Icon = BitmapFactory.DecodeResource(Resources, Resource.Drawable.share),
                Text = "Share"
            };

            editor.ToolbarSettings.ToolbarItems.Add(footerItem);
    
{% endhighlight %}

{% endtabs %}


