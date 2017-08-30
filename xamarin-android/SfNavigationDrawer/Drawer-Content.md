---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.Android
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Sliding Panel Contents
	
The sliding panel contents are divided into three parts and they are as follows
	
* [Drawer Content](#drawer-main-content)
* [Header Content](#drawer-header-content) 
* [Footer Content](#drawer-footer-content)
		
The header and footer contents are optional and Drawer content is the mandatory one which is due to the maximum space allocated for Drawer content view.
		
## Drawer Main Content

The sliding main content of the SfNavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

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

![](images/DrawerContentView.png)

## Drawer Header Content

Gets or sets the header of the DrawerView panel in the SfNavigationDrawer control using `DrawerHeaderView` property.

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

![](images/DrawerHeaderView.png)

## Drawer Footer Content

Gets or sets the footer for the DrawerView panel in the SfNavigationDrawer control using `DrawerFooterView` property.

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

![](images/DrawerFooterView.png)

## Drawer Size

Gets or sets the height and width of the DrawerView panel in the SfNavigationDrawer control using `DrawerHeight` and `DrawerWidth` properties.

{% tabs %}

{% highlight c# %}

navigationDrawer.DrawerHeight = (float)(300);
navigationDrawer.DrawerWidth = (float)(200);

{% endhighlight %}

{% endtabs %}