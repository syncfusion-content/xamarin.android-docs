---
layout: post
title: Various features of Syncfusion® NavigationDrawer control for Android
description: Learn how to configure content view, drawer content view, footer view, header view, drawer size, and multiple drawer settings in NavigationDrawer.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Sliding Panel Contents
	
The sliding panel contents in SfNavigationDrawer are organized into three distinct sections:
* [Drawer Content](#drawer-main-content)
* [Header Content](#drawer-header-content) 
* [Footer Content](#drawer-footer-content)
		
The header and footer contents are optional, while the drawer content is mandatory as it occupies the primary space within the drawer panel.
		
## Drawer Main Content

The main content of the SfNavigationDrawer sliding panel can be configured using the `DrawerContentView` property. This property accepts any desired view to be displayed as the primary drawer content.
{% tabs %}

{% highlight c# %}

namespace navigationDrawerSample
{
    [Activity(Label = "NavigationDrawerSample", MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {
        Button DrawerButton;
        ListView viewItem;
        TextView profileContentLabel;
        ArrayAdapter<string> arrayAdapter;
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);

            SfNavigationDrawer navigationDrawer;
            navigationDrawer = new SfNavigationDrawer(this);

            List<string> positionlist = new List<string>();
            positionlist.Add("Home");
            positionlist.Add("Profile");
            positionlist.Add("Inbox");
            positionlist.Add("Outbox");
            positionlist.Add("Sent Items");
            positionlist.Add("Trash");
            arrayAdapter = new ArrayAdapter<string>(this, Android.Resource.Layout.SimpleListItem1, positionlist);
            viewItem = new ListView(this);
            viewItem.Adapter = arrayAdapter;
            viewItem.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            viewItem.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);

            LinearLayout HomeLayout = new LinearLayout(this);

            profileContentLabel = new TextView(this);
            profileContentLabel.TextSize = 20;
            profileContentLabel.Text = "Home";
            profileContentLabel.SetTextColor(Android.Graphics.Color.Black);
            profileContentLabel.SetBackgroundColor(Android.Graphics.Color.LightBlue);
            profileContentLabel.Gravity = GravityFlags.Center;
            profileContentLabel.LayoutParameters = new ViewGroup.LayoutParams(770, 100);

            HomeLayout.AddView(profileContentLabel);

            LinearLayout contentLayout = new LinearLayout(this);
            contentLayout.Orientation = Orientation.Vertical;

            LinearLayout buttonLayout = new LinearLayout(this);
            buttonLayout.SetBackgroundColor(Android.Graphics.Color.Gray);
            buttonLayout.SetGravity(GravityFlags.Center);

            buttonLayout.LayoutParameters = new LinearLayout.LayoutParams(1000, 1000);

            DrawerButton = new Button(this);
            DrawerButton.Text = "Drawer";
            DrawerButton.LayoutParameters = new LinearLayout.LayoutParams(ViewGroup.LayoutParams.WrapContent, ViewGroup.LayoutParams.WrapContent);
            DrawerButton.Gravity = GravityFlags.Center;

            buttonLayout.AddView(DrawerButton);
            DrawerButton.Click += (sender, e) =>
            {
                navigationDrawer.ToggleDrawer();
            };
            contentLayout.SetBackgroundColor(Android.Graphics.Color.SkyBlue);
            contentLayout.AddView(HomeLayout);
            contentLayout.AddView(buttonLayout);


            FrameLayout frameLayout = new FrameLayout(this);
            frameLayout.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
            frameLayout.AddView(viewItem);
            navigationDrawer.DrawerContentView = frameLayout;

            navigationDrawer.ContentView = contentLayout;

            SetContentView(navigationDrawer);
        }
    }
}

{% endhighlight %}

{% endtabs %}

![NavigationDrawer with custom drawer content](images/DrawerContentView.png)

## Drawer Header Content

The header section of the drawer panel can be configured using the `DrawerHeaderView` property. This allows you to display user information, branding, or navigation elements at the top of the drawer.
{% tabs %}

{% highlight c# %}
namespace navigationDrawerSample
{
	[Activity(Label = "navigationDrawerSample", MainLauncher = true, Icon = "@mipmap/icon")]
	public class MainActivity : Activity
	{
           SfNavigationDrawer navigationDrawer;
           protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            
            navigationDrawer = new SfNavigationDrawer(this);

            ImageView userImg = new ImageView(this);
            userImg.SetImageResource(Resource.Drawable.Icon);
            userImg.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            TextView userName = new TextView(this);
            userName.Text = "James Pollock";
            userName.TextSize = 20;
            userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
            userName.SetTextColor(Android.Graphics.Color.White);
            LinearLayout headerLayout = new LinearLayout(this);
            headerLayout.Orientation = Orientation.Vertical;
            headerLayout.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            headerLayout.SetPadding(0, 20, 0, 0);
            headerLayout.AddView(userImg);
            headerLayout.AddView(userName);
            navigationDrawer.DrawerHeaderView = headerLayout;
            SetContentView(navigationDrawer);
    }
}
}
 
{% endhighlight %}

{% endtabs %}

![NavigationDrawer with header content](images/DrawerHeaderView.png)

## Drawer Footer Content

The footer section of the drawer panel can be configured using the `DrawerFooterView` property. This is typically used for additional actions, settings, or supplementary information.
{% tabs %}

{% highlight c# %}
namespace navigationDrawerSample
{
	[Activity(Label = "navigationDrawerSample", MainLauncher = true, Icon = "@mipmap/icon")]
	public class MainActivity : Activity
	{
            SfNavigationDrawer navigationDrawer;
            protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            navigationDrawer = new SfNavigationDrawer(this);
            TextView userName = new TextView(this);
            userName.Text = "James Pollock";
            userName.Gravity = GravityFlags.Center;
            userName.TextSize = 20;
            userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
            userName.SetTextColor(Android.Graphics.Color.White);
            LinearLayout footerLayout = new LinearLayout(this);
            footerLayout.Orientation = Orientation.Vertical;
            footerLayout.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            footerLayout.SetPadding(0, 20, 0, 0);
            footerLayout.AddView(userName);
            navigationDrawer.DrawerFooterView = footerLayout;
            SetContentView(navigationDrawer);
    }
}
}
       


{% endhighlight %}

{% endtabs %}

![NavigationDrawer with footer content](images/DrawerFooterView.png)

## Drawer Size

You can customize the dimensions of the drawer panel using the `DrawerHeight` and `DrawerWidth` properties to control the drawer's appearance and space utilization.
{% tabs %}

{% highlight c# %}

navigationDrawer.DrawerHeight = (float)(300);
navigationDrawer.DrawerWidth = (float)(200);

{% endhighlight %}

{% endtabs %}

## Multiple Drawers

The SfNavigationDrawer supports multiple drawers that can be opened from different sides of the screen. This functionality is implemented using the `DrawerSettings` class, which provides two types of drawer configurations:
* Default drawer settings
* Secondary drawer settings

N> While header and footer content are optional, drawer content is mandatory to properly allocate space for the drawer functionality.
		
## Default Drawer Settings

The default drawer can be configured using the `DefaultDrawerSettings` property with a `DrawerSettings` instance. The following example demonstrates how to configure the default drawer properties:
{% tabs %}

{% highlight c# %}

DrawerSettings defaultDrawerSettings = new DrawerSettings();
defaultDrawerSettings.DrawerHeight = 150;
defaultDrawerSettings.Position = Position.Left;
defaultDrawerSettings.Transition = Transition.SlideOnTop;
defaultDrawerSettings.ContentBackgroundColor = Color.Red;
defaultDrawerSettings.DrawerWidth = 150;
navigationDrawer.DrawerHeaderHeight = 150;
navigationDrawer.DrawerFooterHeight = 150;
navigationDrawer.DefaultDrawerSettings = defaultDrawerSettings;
  
{% endhighlight %}

{% endtabs %}

N> When using default drawer settings, the NavigationDrawer will use the property values defined within the DrawerSettings class.
### Header View of the Default Drawer

Configure the header content for the default drawer using the `DrawerHeaderView` property within the `DrawerSettings` class:
{% tabs %}

{% highlight c# %}

DrawerSettings defaultDrawerSettings = new DrawerSettings();
TextView userName = new TextView(this);
userName.Text = "James Pollock";
userName.TextSize = 20;
userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
userName.SetTextColor(Android.Graphics.Color.White);
LinearLayout headerLayout = new LinearLayout(this);
headerLayout.Orientation = Orientation.Vertical;
headerLayout.SetPadding(0, 20, 0, 0);
headerLayout.AddView(userName);
defaultDrawerSettings.DrawerHeaderView = headerLayout;

{% endhighlight %}

{% endtabs %}      

### Content View of the Default Drawer

The drawer content can be provided to the default drawer using the `DrawerContentView` property inside the DrawerSettings class. The following code sample demonstrates how to set drawer content to the default drawer.

{% tabs %}

{% highlight c# %}

SfNavigationDrawer navigationDrawer = new SfNavigationDrawer(this);
DrawerSettings defaultDrawerSettings = new DrawerSettings();
defaultDrawerSettings.DrawerHeight = 150;
defaultDrawerSettings.Position = Position.Left;
List<string> positionlist = new List<string>();
positionlist.Add("Home");
positionlist.Add("Profile");
positionlist.Add("Inbox");
positionlist.Add("Outbox");
arrayAdapter = new ArrayAdapter<string>(this, Android.Resource.Layout.SimpleListItem1, positionlist);
viewItem = new ListView(this);
viewItem.Adapter = arrayAdapter;
viewItem.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
FrameLayout frameLayout = new FrameLayout(this);
frameLayout.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
frameLayout.AddView(viewItem);
defaultDrawerSettings.DrawerContentView = frameLayout;
navigationDrawer.DefaultDrawerSettings = defaultDrawerSettings;
SetContentView(navigationDrawer);
  
{% endhighlight %}

{% endtabs %}   

### Footer View of the Default Drawer

Configure the footer content for the default drawer using the `DrawerFooterView` property within the `DrawerSettings` class:
{% tabs %}

{% highlight c# %}

DrawerSettings defaultDrawerSettings = new DrawerSettings();
TextView userName = new TextView(this);
userName.Text = "James Pollock";
userName.TextSize = 20;
userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
userName.SetTextColor(Android.Graphics.Color.White);
LinearLayout footerLayout = new LinearLayout(this);
footerLayout.Orientation = Orientation.Vertical;
footerLayout.SetPadding(0, 20, 0, 0);
footerLayout.AddView(userName);
defaultDrawerSettings.DrawerFooterView = footerLayout;

{% endhighlight %}

{% endtabs %}   

## Secondary Drawer Settings

The secondary drawer provides the same functionality as the default drawer but can be positioned differently. Configure it using the `SecondaryDrawerSettings` property:
{% tabs %}

{% highlight c# %}

DrawerSettings secondaryDrawerSettings = new DrawerSettings();
secondaryDrawerSettings.DrawerHeight = 150;
secondaryDrawerSettings.Position = Position.Left;
secondaryDrawerSettings.Transition = Transition.SlideOnTop;
secondaryDrawerSettings.ContentBackgroundColor = Color.Red;
secondaryDrawerSettings.DrawerWidth = 150;
navigationDrawer.DrawerHeaderHeight = 150;
navigationDrawer.DrawerFooterHeight = 150;
navigationDrawer.SecondaryDrawerSettings = secondaryDrawerSettings;

  
{% endhighlight %}

{% endtabs %}

N> When both default and secondary drawers are positioned on the same side, the default drawer will take precedence during swipe gestures.

### Header View of the Secondary Drawer

The header content can be provided to the secondary drawer using the `DrawerHeaderView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code sample demonstrates how to set the header content to the secondary drawer.

{% tabs %}

{% highlight c# %}

DrawerSettings secondaryDrawerSettings = new DrawerSettings();
TextView userName = new TextView(this);
userName.Text = "James Pollock";
userName.TextSize = 20;
userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
userName.SetTextColor(Android.Graphics.Color.White);
LinearLayout headerLayout = new LinearLayout(this);
headerLayout.Orientation = Orientation.Vertical;
headerLayout.SetPadding(0, 20, 0, 0);
headerLayout.AddView(userName);
secondaryDrawerSettings.DrawerHeaderView = headerLayout;

{% endhighlight %}

{% endtabs %}      

### Content View of the Secondary Drawer

The drawer content can be provided to the secondary drawer using the `DrawerContentView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code sample demonstrates how to set the drawer content to the secondary drawer.

{% tabs %}

{% highlight c# %}

SfNavigationDrawer navigationDrawer = new SfNavigationDrawer(this);
DrawerSettings secondaryDrawerSettings = new DrawerSettings();
secondaryDrawerSettings.DrawerHeight = 150;
secondaryDrawerSettings.Position = Position.Left;
List<string> positionlist = new List<string>();
positionlist.Add("Home");
positionlist.Add("Profile");
positionlist.Add("Inbox");
positionlist.Add("Outbox");
arrayAdapter = new ArrayAdapter<string>(this, Android.Resource.Layout.SimpleListItem1, positionlist);
viewItem = new ListView(this);
viewItem.Adapter = arrayAdapter;
viewItem.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
FrameLayout frameLayout = new FrameLayout(this);
frameLayout.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
frameLayout.AddView(viewItem);
secondaryDrawerSettings.DrawerContentView = frameLayout;
navigationDrawer.SecondaryDrawerSettings = secondaryDrawerSettings;
SetContentView(navigationDrawer);

{% endhighlight %}

{% endtabs %}   

### Footer View of the Secondary Drawer

The footer content can be provided to the secondary drawer using the `DrawerFooterView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code sample demonstrates how to set footer content to the secondary drawer.

{% tabs %}

{% highlight c# %}

DrawerSettings secondaryDrawerSettings = new DrawerSettings();
TextView userName = new TextView(this);
userName.Text = "James Pollock";
userName.TextSize = 20;
userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
userName.SetTextColor(Android.Graphics.Color.White);
LinearLayout footerLayout = new LinearLayout(this);
footerLayout.Orientation = Orientation.Vertical;
footerLayout.SetPadding(0, 20, 0, 0);
footerLayout.AddView(userName);
secondaryDrawerSettings.DrawerFooterView = footerLayout;

{% endhighlight %}

{% endtabs %}   

## Toggling Methods

Users can toggle the secondary drawer using the `ToggleSecondaryDrawer` method. 

{% highlight c# %} 

navigationDrawer.ToggleSecondaryDrawer();

{% endhighlight %}

### Opening the drawer programmatically

The `IsOpen` property in the DrawerSettings of SecondaryDrawerSettings is used to open or close the drawer programmatically.

N> Users can open only one drawer at a time.
