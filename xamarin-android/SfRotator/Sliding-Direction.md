---
layout: post
title: Navigation Direction in Xamarin.Android Rotator | Syncfusion®
description: Learn how to configure navigation directions and sliding behavior in the Rotator control for Xamarin.Android platform
platform: xamarin.android 
control: Rotator
documentation: ug
---

# Navigation Direction in Xamarin.Android Rotator Control

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

## Horizontal

Items can be navigated in horizontal direction.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

### Vertical Navigation

Vertical navigation enables top-to-bottom and bottom-to-top movement between items. This direction is useful for specific design layouts and content types.
{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

## Unidirectional Navigation

Unidirectional navigation restricts movement to a single direction, which can be useful for guided experiences, presentations, or specific design requirements.

### Left-to-Right Navigation

Restricts navigation to left-to-right movement only, preventing backward navigation.
{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.LeftToRight;

{% endhighlight %}

### Right-to-Left Navigation

Restricts navigation to right-to-left movement only, useful for RTL languages or specific design patterns.
{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.RightToLeft;

{% endhighlight %}

### Top-to-Bottom Navigation

Restricts navigation to downward movement only, creating a top-down flow experience.
{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.TopToBottom;

{% endhighlight %}

### Bottom-to-Top Navigation

Restricts navigation to upward movement only, creating a bottom-up flow experience.
{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.BottomToTop;

{% endhighlight %}
