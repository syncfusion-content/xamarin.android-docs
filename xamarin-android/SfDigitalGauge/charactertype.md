---
layout: post
title: Character type of Digital gauge in Xamarin.Android
description: Learn how to define character type in DigitalGauge
platform: Xamarin.Android
control: DigitalGauge
documentation: ug
---

# CharacterType

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> SegmentSeven is the default CharacterType in the SfDigitalGauge.

## SevenSegment

{% highlight c# %}

	 digitalGauge.CharacterType=CharacterTypes.SegmentSeven;

{% endhighlight %}

![](images/SegmentSeven.png)

## Fourteen Segment

 {% highlight c# %}

	 digitalGauge.CharacterType=CharacterTypes.segmentFourteen;

{% endhighlight %}

![](images/SegmentFourteen.png)

## Sixteen Segment

{% highlight c# %}

	 digitalGauge.CharacterType=CharacterTypes.segmentSixteen;

{% endhighlight %}

![](images/SegmentSixteen.png)

## EightCrossEightDotMatrix Segment

{% highlight c# %}

	 digitalGauge.CharacterType=CharacterTypes.EightCrossEightDotMatrix;

{% endhighlight %}

![](images/SegmentMatrix.png)

