---
layout: post
title: RTL | TreeView for Xamarin.Android | Syncfusion
description: Describes how to enable right-to-left localization treeview.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Right to left(RTL)

TreeView supports the right-to-left localization by setting [LayoutDirection](https://developer.xamarin.com/api/type/Android.Views.LayoutDirection/) to `Rtl`.TreeView also supports RTL when device layout direction is changed.

N> Specific platform setup is required to enable right-to-left localization. For platform settings you can refer [here](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/localization/right-to-left#platform-setup).

{% tabs %}
{% highlight c# %}

SfTreeView treeView = new SfTreeView();
treeView.LayoutDirection = LayoutDirection.Rtl;

{% endhighlight %}
{% endtabs %}

N> If you need to customize [Adapter](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeView.Android~Syncfusion.Android.TreeView.SfTreeView~Adapter.html) with your custom views, layout the views in application based on [LayoutDirection](https://developer.xamarin.com/api/type/Android.Views.LayoutDirection/) to respond for right-to-left localization.

{% tabs %}
{% highlight c# %}
//customized view to support rtl
public class NodeImageView : LinearLayout
{
    #region Fields

    private ContentLabel label1;
    private ImageViewExt imageIcon;
    SfTreeView view;

    #endregion

    #region Constructor

    public NodeImageView(Context context, SfTreeView treeView) : base(context)
    {
        view = treeView;
        this.Orientation = Orientation.Horizontal;
        label1 = new ContentLabel(context);
        label1.Gravity = GravityFlags.CenterVertical;
        if(view.LayoutDirection == Android.Views.LayoutDirection.Rtl)
            TextDirection.Rtl;
        imageIcon = new ImageViewExt(context);
        this.AddView(imageIcon);
        this.AddView(label1);
    }

    #endregion

    #region Methods

    protected override void OnMeasure(int widthMeasureSpec, int heightMeasureSpec)
    {
        var density = Resources.DisplayMetrics.Density;
        var measuredWidth = (int)(40 * density);
        var measuredHeight = (int)(45 * density);
        var labelWidth = Math.Abs(widthMeasureSpec - measuredWidth);
        this.label1.SetMinimumHeight(measuredHeight);
        this.label1.SetMinimumWidth(labelWidth);
        this.imageIcon.SetMinimumHeight(measuredHeight);
        this.imageIcon.SetMinimumWidth(measuredWidth);
        this.imageIcon.Measure(measuredWidth, measuredHeight);
        this.label1.Measure(labelWidth, measuredHeight);
        base.OnMeasure(widthMeasureSpec, heightMeasureSpec);
    }

    protected override void OnLayout(bool changed, int l, int t, int r, int b)
    {
        var density = Resources.DisplayMetrics.Density;
        var measuredWidth = (int)(40 * density);
        var measuredHeight = (int)(45 * density);
        if (view.LayoutDirection == Android.Views.LayoutDirection.Rtl)
        {
            this.imageIcon.Layout(Width- measuredWidth, 0, Width, measuredHeight);
            this.label1.Layout(0, 0, Width- measuredWidth, measuredHeight);
        }
        else
        {
            this.imageIcon.Layout(0, 0, measuredWidth, measuredHeight);
            this.label1.Layout(measuredWidth, 0, Width, measuredHeight);
        }
    }

    #endregion
}

![Xamarin Android TreeView with right-to-left localization](Images/Right-To-Left-Xamarin-Android-TreeView.png)