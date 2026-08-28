---
layout: post
title: Transition of drawer in Syncfusion® NavigationDrawer control for Xamarin.Android
description: Learn how to configure transition animations for the DrawerView panel, including SlideOnTop, Push, and Reveal effects with best practices and performance considerations.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---
# Drawer Opening Animation

The `Transition` property controls the animation behavior when the drawer opens and closes, providing different visual effects that can enhance your application's user experience. The property offers three distinct animation types, each creating a unique interaction pattern:
* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

## SlideOnTop

Slides the DrawerContent on top of the main content.

{% highlight c# %} 

	 Transition sliderTransition = Transition.SlideOnTop;
	 navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/Slide-on-top.png)

## Push

This transition slides the Drawer and main content simultaneously.

{% highlight c# %} 

	 Transition sliderTransition = Transition.Push;
	 navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/Push.png)

## Reveal

This transition keeps the Drawer content in fixed position and the main content will be slide to reveal the drawer content.

{% highlight c# %} 

	Transition sliderTransition = Transition.Reveal;
	navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/reveal.png)
