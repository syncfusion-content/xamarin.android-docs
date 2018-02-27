---
layout : post
title : Serialization in Syncfusion SfImageEditor control in Xamarin.Android
description : Learn how to Serialize and deserilaie edited shapes in ImageEditor for Xamarin.Android
platform : Xamarin.Android
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle,Arrow,Rectangle), free hand drawing,Text and Toolbar settings. Save the current state of the Image Editor and Load it back when its needed.

## Serialization
  To serialize the shapes like circle,arrow,rectangle,text ,freehand drawing and toolbar settings by calling SaveEdits() method.Serialized object will be return in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor = new   SfImageEditor(this);
	 Stream stream=editor.SaveEdits();
     SetContentView(editor);
    
	
{% endhighlight %}

{% endtabs %}

   convert the stream into string and save as .txt format file and add into a asset folder and also set as AndroidAsset.
   In Xamarin.Android.Text file like this
  [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       


## Deserialization
   To deserialize serialized objects by calling LoadEdits(stream) method .Deserialize the object by using loaded JSON stream.

{% tabs %}

{% highlight C# %}
        
		 public class MainActivity : Activity
    {

        SfImageEditor editor;
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);
            editor = new SfImageEditor(this);
            DelayActionAsync(1500, LoadStream);
            SetContentView(editor);
        }
        public async Task DelayActionAsync(int delay, Action action)
        {
            await Task.Delay(delay);
            action();
        }

        void LoadStream()
        {

            using (StreamReader src = new StreamReader(Assets.Open("Chart.txt")))
            {
                string content = src.ReadToEnd();
                byte[] byteArray = Encoding.ASCII.GetBytes(content);
                MemoryStream stream = new MemoryStream(byteArray);
                if (stream != null)
                    editor.LoadEdits(stream);

            }
        }
    }
		
        

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)
