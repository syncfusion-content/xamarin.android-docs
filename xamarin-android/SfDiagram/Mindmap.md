---
title: Add mindmap for diagram
description: Learn how to add mindmap in diagram
platform: Xamarin.Android
control: SfDiagram
documentation: UG
keywords: 
---
# Mind map layout
A mind map is a diagram used to visually organize the information. It is hierarchical and shows relationship of the whole idea. It consists of a central ideas, related ideas, and lines connecting them together.  It is used for brainstorming, planning, and information gathering etc. The following code example illustrates how to create and mind map layout:
{% tabs %}
{% highlight c# %}
SfDiagram diagram;
        string x;
        List<Color> FColor = new List<Color>();
        List<Color> SColor = new List<Color>();
        Random random = new Random();
        int index;
        int width = 150; int height = 75;

        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);

            // Set our view from the "main" layout resource
            SetContentView(Resource.Layout.Main);
            LinearLayout linearLayout = FindViewById<LinearLayout>(Resource.Id.linearlayout);
            diagram = new SfDiagram(this);
            diagram.LayoutParameters = new LayoutParams(LayoutParams.MatchParent, LayoutParams.MatchParent);

            LinearLayout linearLayout2 = new LinearLayout(this);
            linearLayout2.Orientation = Android.Widget.Orientation.Horizontal;
            linearLayout2.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, Resources.DisplayMetrics.HeightPixels - 400);
            linearLayout.AddView(linearLayout2);
            linearLayout2.AddView(diagram);

            linearLayout2 = new LinearLayout(this);
            linearLayout2.Orientation = Android.Widget.Orientation.Horizontal;
            linearLayout2.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, Resources.DisplayMetrics.HeightPixels - 400);
            linearLayout.AddView(linearLayout2);

            //Alternate color selection for child nodes
            SColor.Add(Color.Blue);
            SColor.Add(Color.AliceBlue);
            SColor.Add(Color.Aquamarine);
            SColor.Add(Color.Bisque);
            SColor.Add(Color.BlanchedAlmond);
            SColor.Add(Color.BlueViolet);
            FColor.Add(Color.Brown);
            FColor.Add(Color.DarkGray);
            FColor.Add(Color.DarkViolet);
            FColor.Add(Color.Gold);
            FColor.Add(Color.Green);
            FColor.Add(Color.Indigo);

            //Add Root node
            var node = AddNode(300, 400, width, height, "Goals");
            AddNodeStyle(node, Color.Lavender, Color.Black);
            diagram.AddNode(node);

            //Add child nodes for root node
            var ch1node = AddNode(100, 100, width, height, "Financial");
            index = random.Next(5);
            AddNodeStyle(ch1node, FColor[index], SColor[index]);
            diagram.AddNode(ch1node);

            var ch1childnode = AddNode(100, 100, width, height, "Investment");
            AddNodeStyle(ch1childnode, (ch1node.Style.Brush as SolidBrush).FillColor, (ch1node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch1childnode);

            var ch2node = AddNode(100, 600, width, height, "Social");
            index = random.Next(5);
            AddNodeStyle(ch2node, FColor[index], SColor[index]);
            diagram.AddNode(ch2node);

            var ch2childnode1 = AddNode(100, 100, width, height, "Friends");
            AddNodeStyle(ch2childnode1, (ch2node.Style.Brush as SolidBrush).FillColor, (ch2node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch2childnode1);

            var ch2childnode2 = AddNode(100, 100, width, height, "Family");
            AddNodeStyle(ch2childnode2, (ch2node.Style.Brush as SolidBrush).FillColor, (ch2node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch2childnode2);

            var ch3node = AddNode(500, 100, width, height, "Personal");
            index = random.Next(5);
            AddNodeStyle(ch3node, FColor[index], SColor[index]);
            diagram.AddNode(ch3node);

            var ch3childnode1 = AddNode(500, 100, width, height, "Sports");
            AddNodeStyle(ch3childnode1, (ch3node.Style.Brush as SolidBrush).FillColor, (ch3node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch3childnode1);

            var ch3childnode2 = AddNode(500, 100, width, height, "Food");
            AddNodeStyle(ch3childnode2, (ch3node.Style.Brush as SolidBrush).FillColor, (ch3node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch3childnode2);

            var ch4node = AddNode(500, 600, width, height, "Work");
            index = random.Next(5);
            AddNodeStyle(ch4node, FColor[index], SColor[index]);
            diagram.AddNode(ch4node);

            var ch4childnode1 = AddNode(500, 100, width, height, "Project");
            AddNodeStyle(ch4childnode1, (ch4node.Style.Brush as SolidBrush).FillColor, (ch4node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch4childnode1);

            var ch4childnode2 = AddNode(500, 100, width, height, "Career");
            AddNodeStyle(ch4childnode2, (ch4node.Style.Brush as SolidBrush).FillColor, (ch4node.Style.StrokeBrush as SolidBrush).FillColor);
            diagram.AddNode(ch4childnode2);

            //Add connector 
            diagram.AddConnector(AddConnector(node, ch1node));
            diagram.AddConnector(AddConnector(node, ch2node));
            diagram.AddConnector(AddConnector(node, ch3node));
            diagram.AddConnector(AddConnector(node, ch4node));
            diagram.AddConnector(AddConnector(ch1node, ch1childnode));
            diagram.AddConnector(AddConnector(ch2node, ch2childnode1));
            diagram.AddConnector(AddConnector(ch2node, ch2childnode2));
            diagram.AddConnector(AddConnector(ch3node, ch3childnode1));
            diagram.AddConnector(AddConnector(ch3node, ch3childnode2));
            diagram.AddConnector(AddConnector(ch4node, ch4childnode1));
            diagram.AddConnector(AddConnector(ch4node, ch4childnode2));

        }
//Add connector method 
        private Connector AddConnector(Node node, Node ch1node)
        {
            var c1 = new Connector(this);
            c1.SourceNode = node;
            c1.TargetNode = ch1node;
            c1.Style.StrokeBrush = new SolidBrush((c1.TargetNode.Style.StrokeBrush as SolidBrush).FillColor);
            c1.Style.StrokeStyle = StrokeStyle.Dashed;
            c1.Style.StrokeWidth = 3;
            c1.TargetDecoratorStyle.StrokeWidth = c1.TargetDecoratorStyle.StrokeWidth;
            c1.TargetDecoratorStyle.Fill = (c1.TargetNode.Style.StrokeBrush as SolidBrush).FillColor;
            c1.TargetDecoratorStyle.StrokeColor = (c1.TargetNode.Style.StrokeBrush as SolidBrush).FillColor;
            c1.SegmentType = SegmentType.CurveSegment;
            return c1;
        }

        //Add node style method
        private void AddNodeStyle(Node node, Color fill, Color Stroke)
        {
            node.Style.Brush = new SolidBrush(fill);
            node.Style.StrokeBrush = new SolidBrush(Stroke);
        }

        //Add node method 
        Node AddNode(int x, int y, int w, int h, string text)
        {
            var node = new Node(this);
            node.OffsetX = x;node.OffsetY = y;
            node.Width = w;node.Height = h;
            node.ShapeType = ShapeType.RoundedRectangle;
            node.Style.StrokeWidth = 3;
            node.Annotations.Add(new Annotation() { Content = text, FontSize = 14 , TextBrush = new SolidBrush(Color.Black) });
            return node;
        }
{% endhighlight %}
{% endtabs %}

## Initializing the mind map layout
The following code illustrates how to initialize the mind map layout in diagram loaded event:
{% tabs %}
{% highlight c# %}
//Diagram loaded event
diagram.Loaded += Diagram_Loaded;

private void Diagram_Loaded(object sender)
{
      diagram.LayoutManager = new LayoutManager()
      {
         Layout = new MindMapLayout()
         {
            MindMapOrientation = Orientation.Horizontal,
            HorizontalSpacing = 70,
         }
      };
      //Updating the layout
      diagram.LayoutManager.Layout.UpdateLayout();
}

{% endhighlight %}
{% endtabs %}
![](Mindmap_images/Mindmap_img1.jpeg)

## Mind map layout style
Mind map styles are defined as collection of node style with a single connector style. Collection of node style will apply from root node to leaf node either through branch wise or level wise.
## Branch wise node style
Defined node style collection will be applied from branch wise by setting “ApplyNodeStyleBy” property as Branch. The following code example illustrates how to apply style for mind map level wise.
{% tabs %}
{% highlight c# %}
private void UpdateTheme()
        {
            bool m_repeatmode = true;
            nodeStyleCollection.Clear();
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#d7ebf6")), Color.ParseColor("#d7ebf6"), objShape1, StrokeStyle.Default,
            new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#ffebc4")), Color.ParseColor("#ffebc4"), objShape2, StrokeStyle.Default,
                new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#ffcdcd")), Color.ParseColor("#ffcdcd"), objShape3, StrokeStyle.Default,
             new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            lineStyle = new LineStyle(segment, StrokeStyle.Default, 2, connLineApplyColorFrom, Dectype, connDecApplyColorFrom, connDecApplyColorFrom) { Color = connColor };
            (diagram.LayoutManager.Layout as MindMapLayout).UpdateLayoutStyle(new LayoutStyle(nodeStyleCollection, lineStyle, ApplyNodeStyleBy. Branch, m_repeatmode));
        }
        private void Diagram_Loaded(object sender)
        { 
            UpdateTheme();
        }
{% endhighlight %}
{% endtabs %}
![](Mindmap_images/Mindmap_img2.jpeg)

## Level wise node style
Defined node style collection will be applied from level wise by setting “ApplyNodeStyleBy” property as Level. The following code example illustrates how to apply style for mind map level wise.
{% tabs %}
{% highlight c# %}
private void UpdateTheme()
        {
            bool m_repeatmode = true;
            nodeStyleCollection.Clear();
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#d7ebf6")), Color.ParseColor("#d7ebf6"), objShape1, StrokeStyle.Default,
            new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#ffebc4")), Color.ParseColor("#ffebc4"), objShape2, StrokeStyle.Default,
                new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            nodeStyleCollection.Add(new NodeStyle(new SolidBrush(Color.ParseColor("#ffcdcd")), Color.ParseColor("#ffcdcd"), objShape3, StrokeStyle.Default,
             new Syncfusion.SfDiagram.Android.TextStyle((int)(14), Color.Black, ".SF UI Text", HorizontalAlignment.Center, VerticalAlignment.Center)));
            lineStyle = new LineStyle(segment, StrokeStyle.Default, 2, connLineApplyColorFrom, Dectype, connDecApplyColorFrom, connDecApplyColorFrom) { Color = connColor };
            (diagram.LayoutManager.Layout as MindMapLayout).UpdateLayoutStyle(new LayoutStyle(nodeStyleCollection, lineStyle, ApplyNodeStyleBy.Level, m_repeatmode));
        }
        private void Diagram_Loaded(object sender)
        { 
            UpdateTheme();
        }
{% endhighlight %}
{% endtabs %}
![](Mindmap_images/Mindmap_img3.jpeg)

## Repeat mode
When style collection ends, still next level/ branch can have styles. To be cyclic, enable repeat mode. Else to continue with last style disable it.

