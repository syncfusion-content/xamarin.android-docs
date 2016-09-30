---
layout: post
title: Character type of Digital gauge in Xamarin.Android
description: Learn how to define character type in DigitalGauge
platform: Xamarin.Android
control: DigitalGauge
documentation: ug
---

# Various-types-of-Segment

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> SegmentSeven is the default CharacterType in the SfDigitalGauge.

## SevenSegment

{% tabs %}

{% highlight c# %}

digitalGauge.CharacterType=CharacterTypes.SegmentSeven;

{% endhighlight %}

{% endtabs %}

![](images/SegmentSeven.png)

## Fourteen Segment

{% tabs %}

{% highlight c# %}

digitalGauge.CharacterType=CharacterTypes.segmentFourteen;

{% endhighlight %}

{% endtabs %}

![](images/SegmentFourteen.png)

## Sixteen Segment

{% tabs %}

{% highlight c# %}

digitalGauge.CharacterType=CharacterTypes.segmentSixteen;

{% endhighlight %}

{% endtabs %}

![](images/SegmentSixteen.png)

## EightCrossEightDotMatrix Segment

{% tabs %}

{% highlight c# %}

digitalGauge.CharacterType=CharacterTypes.EightCrossEightDotMatrix;

{% endhighlight %}

{% endtabs %}

![](images/SegmentMatrix.png)

