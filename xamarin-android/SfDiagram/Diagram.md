---
title: Diagram for Essential&reg; Xamarin.Android Diagram | Syncfusion&reg;
description: Learn here all about Diagram support in Syncfusion<sup>&reg;</sup>; Diagram (SfDiagram) control in Xamarin.Android, its elements and more.
platform: xamarin.android
control: SfDiagram
documentation: UG
keywords: 
---
# Diagram in Xamarin Diagram (SfDiagram)
The diagram control allows to create different types of diagrams such as flow charts, use case diagrams, workflow process diagrams, and more

## Page settings
The Page settings are enabled to customize the appearance, width, and height of the diagram page. The size and appearance of the diagram pages can be customized with the PageSettings property.
The PageWidth and PageHeight properties of page settings define the size of the page. You can also customize the appearance of off-page regions with the BackgroundColor property.
The following code illustrates how to customize the page size and appearance of the page and off-page:
{% tabs %}
{% highlight c# %}
//Sets Page background
diagram.BackgroundColor = Color.Lime;
//Sets Page size 
diagram.PageSettings.PageWidth = 500;
diagram.PageSettings.PageHeight = 500;
//Customizes the appearance of Page
diagram.PageSettings.PageBackGround= Color.White;
{% endhighlight %}
{% endtabs %}

## View Port Start Position
Page settings enable you to customize the viewport start position of the diagram page. The enum `ViewPort Start Position` has two constants: Default, Origin. The default value is set to Default.

### Default 
The viewport of the diagram page is decided based on the node's offsets. 

N> The viewport of the diagram page will be in a negative region when the node’s offsets are negative.  

### Origin
The viewport of the diagram page begins with origin (0,0) even though when the node’s offsets are negative.

The following code explains how to customize the view port start position of the page.

{% tabs %}
{% highlight c# %}
//Sets the viewport start position.
SfDiagram.PageSettings.ViewPortStartPosition = ViewportStartPosition.Origin;
{% endhighlight %}
{% endtabs %}

## Stencil:
Stencil has a collection of symbols. It is used to clone the desired symbol by dragging it from the stencil and dropping it into the SfDiagram.
The following code snippet illustrates how to add the stencil:
{% tabs %}
{% highlight c# %}
Stencil stencil = new Stencil();
linearLayout.AddView(stencil);
{% endhighlight %}
{% endtabs %}

## Diagram constraints
The constraints property of diagram allows you to enable or disable certain features.
This will enable or disable the following node behavior.
* Drag
* Resize
* Rotate
* AnnotationEditing
* EnableSelectors
* EnableZoomAndPan
* IsReadOnly

**Example**
The following code illustrates how to disable the item dragging.
{% tabs %}
{% highlight c# %}
SfDiagram diagram = new SfDiagram(this);
// Disable the item dragging
diagram.EnableDrag = false;
linearLayout.AddView(diagram);
{% endhighlight %}
{% endtabs %}

## Diagram style settings
It is easier to apply default rendering styles to all shapes, connectors, stencil symbol, and stencil header in a diagram. Pass the following arguments to diagram style setting constructor: 
 * DefaultNodeStyle argument: Defines the node style properties. 
 * DefaultConnectorStyle argument: Defines the connector style properties.
 * DefaultSymbolStyle argument: Defines the symbol style properties. 
 * DefaultHeaderStyle argument: Defines the header style properties. 

The following code shows how to define the diagram style settings for the diagram object.

{% tabs %}
{% highlight c# %}
// Diagram style settings 
Style NodeStyle = new Style() { Brush = new SolidBrush(Color.Blue), StrokeBrush = new SolidBrush(Color.Brown), StrokeWidth = 2, StrokeStyle = StrokeStyle.Dashed };

Style ConnectorStyle = new Style() { StrokeBrush = new SolidBrush(Color.DeepSkyBlue), StrokeWidth = 3, StrokeStyle = StrokeStyle.Dotted };

SymbolStyle SymbolStyle = new SymbolStyle() { Width = 70, Height = 70, StrokeWidth = 3, StrokeColor = Color.Red };

HeaderStyle HeaderStyle = new HeaderStyle() { FontSize = 24, TextBrush = Color.White, Fill = Color.SteelBlue, FontStyle = FontStyle.Italic, HorizontalAlignment = HorizontalAlignment.Center };

DiagramStyleSettings diagramStyleSettings = new DiagramStyleSettings(NodeStyle, ConnectorStyle, SymbolStyle, HeaderStyle);

//Pass diagram style settings instance to SfDiagram constructor argument  
SfDiagram diagram = new SfDiagram(this ,diagramStyleSettings);
{% endhighlight %}
{% endtabs %}

## Zooming enhancement 
Supports customizing the zoom levels. You can set minimum zoom level value to 0.01f and maximum to ‘infinite’. 
{% tabs %}
{% highlight c# %}
// Define the minimum and maximum zoom factor value 

  diagram.MinimumZoomFactor = 0.01f;
  diagram.MaximumZoomFactor = 5.00f;

{% endhighlight %}
{% endtabs %}

