---
layout: post
title: Concepts and Features | PullToRefresh | Xamarin.Android | Syncfusion
description: concepts and features
platform: Xamarin.Android
control: PullToRefresh
documentation: ug
--- 

# Concepts and Features

## PullingThreshold

Gets or sets the threshold value from the edges for easy panning from the edges. The default value of TouchThreshold is 3 times the RefreshContentHeight.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullingThreshold = 225d;

{% endhighlight %}

{% endtabs %} 

## PullableContent

PullableContent is the main view of the PullToRefresh control on which the desired items can be placed.

{%highlight c#%}

    LinearLayout layout = new LinearLayout (context);
	layout.SetBackgroundColor (Color.AliceBlue);
	pullToRefresh.PullableContent = layout;

{%endhighlight%}


## RefreshContentHeight

`RefreshContentHeight` sets the height of the refresh content.

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshContentHeight = 200d;

{% endhighlight %}

{% endtabs %}

## Refresh ()

Refresh method is used to Refresh the `PullableContent` and also hides the `RefreshContent`.

{% highlight c# %}

    pullToRefresh.Refresh();

{% endhighlight %}

## Transition

The Transition property specifies the animations for the RefreshContent. Transition property has the following two options:

* `SlideOnTop`
* `Push`

The default transition is `SlideOnTop`. That draws the `RefreshContent` on top of the `PullableContent`.

{% tabs %}



{% highlight c# %}

    pullToRefresh.Transition = Transition.SlideOnTop;

{% endhighlight %}

{% endtabs %}

![](features_images/Overview_img1.png)


The following code example shows how to set `Transition` as `Push` to SfPullToRefresh. This transition moves the refresh content and main content simultaneously.

{% tabs %}



{% highlight c# %}

    pullToRefresh.Transition = Transition.Push;

{% endhighlight %}

{% endtabs %}


![](features_images/Overview_img2.png)

## PullDirection

PullDirection property specifies the position of the transition to take place.PullDirection property has the following two options:
* `Top`
* `Bottom`

The default PullDirection is `Top`. That draws the `RefreshContent` on top of the `PullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Top;

{% endhighlight %}

{% endtabs %}

The following code example shows how to set `PullDirection` as `Bottom` to SfPullToRefresh.That draws the `RefreshContent` on Bottom of the `PullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Bottom;

{% endhighlight %}

{% endtabs %}
