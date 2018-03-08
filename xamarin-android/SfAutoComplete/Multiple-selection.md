---
layout : post
title : Multipe Selection in Syncfusion SfAutoComplete control for Xamarin.Android
description : Learn how to select multiple items in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Multiple Selection

Select multiple items from a suggestion list. There are two ways to perform multi selection in autocomplete.

* Token Representation

* Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

<<<<<<< HEAD
=======
{% tabs %}

{% highlight C# %}
	
	
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Token;
	countryAutoComplete.TokensWrapMode=TokensWrapMode.Wrap;
	 
{% endhighlight %}

{% endtabs %}

>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
### Wrap Mode of Token

The selected item can be displayed as token inside SfAutoComplete in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the SfAutoComplete.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight C# %}

<<<<<<< HEAD
public class Employee
{
    public string Name { get; set; }
    public string Image { get; set; }
    public Employee(string name, string image)
{
	this.Name = name;
	this.Image = image;

}
}
    ObservableCollection<Employee> employeeDetails;
    LinearLayout linearLayout = new LinearLayout(this);
	linearLayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
	linearLayout.SetBackgroundColor(Android.Graphics.Color.White);

	SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
	countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

    employeeDetails = new ObservableCollection<Employee>();
	employeeDetails.Add(new Employee("Jack", "jack.png"));
	employeeDetails.Add(new Employee("John", "john.png"));
	employeeDetails.Add(new Employee("James", "james.png"));
	employeeDetails.Add(new Employee("Jacob", "jacob.png"));
	employeeDetails.Add(new Employee("Joy", "joy.png"));
	employeeDetails.Add(new Employee("Victoria", "victoria.png"));

	countryAutoComplete.DisplayMemberPath = "Name";
	countryAutoComplete.DataSource = employeeDetails;
	countryAutoComplete.MultiSelectMode = MultiSelectMode.Token;
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.MaximumDropDownHeight = 200;
	countryAutoComplete.DropDownItemHeight = 50;
	countryAutoComplete.ImageMemberPath = "Image";
	countryAutoComplete.TokensWrapMode = TokensWrapMode.Wrap;

	linearLayout.AddView(countryAutoComplete);
	SetContentView(linearLayout);
=======
public class Student
	{
		string Name;
		string Image;
		public Student(string name,string image)
		{
			this.Name = name;
			this.Image = image;

		}
		public string getName()
		{
			return Name;
		}
		public string getImage()
		{
			return Image;
		}
	}

public NSMutableArray StudentDetails
		{
			get;
			set;
		}

		void GetStudentData()
		{
			NSMutableArray array = new NSMutableArray();
			array.Add(getDictionary("John", "a1.png"));
			array.Add(getDictionary("James", "a2.png"));
			array.Add(getDictionary("Jacob", "a3.png"));
			array.Add(getDictionary("Joy", "a4.png"));
			array.Add(getDictionary("Victoria", "a5.png"));
			array.Add(getDictionary("James", "a6.png"));

			StudentDetails = array;
		}

		NSDictionary getDictionary(string name, string image)
		{

			object[] objects = new object[2];
			object[] keys = new object[2];
			keys.SetValue("Name", 0);
			keys.SetValue("Image", 1);
			objects.SetValue((NSString)name, 0);
			objects.SetValue((NSString)image, 1);
			return NSDictionary.FromObjectsAndKeys(objects, keys);
		}
	 
	
	ArrayAdapter<Object> arrayDataAdapters = new ArrayAdapter<Object>(context,Android.Resource.Layout.SimpleListItem1, array);
	StudentDetails.MultiSelectMode=MultiSelectMode.Token;
	studentAutoComplete.DataSource = arrayDataAdapters;

// Set the TokensWrapMode into Wrap.

	StudentDetails.TokensWrapMode=TokensWrapMode.Wrap;

	TokensSetting token = new TokensSetting();
	token.FontSize=15;
	token.CornerRadius=5;
	token.SetTextColor(Color.Red);
	token.SetBackgroundColor(Color.Gray);
	token.SelectedBackgroundColor(Color.Yellow);
	token.SetDeleteButtonColor(Color.Maroon);
    token.IsCloseButtonVisible=true;
	StudentDetails.TokensSetting= token;
>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a

	
{% endhighlight %}

{% endtabs %}

![](images/TokenRepresentationWrap.png)

### Token Customization

Customization can be done for Token. There are various ways to customize the tokens. They are as follows.

* `TextColor` - sets the color of the text inside the token.

* `FontSize` - sets the size of the Font inside the token.

* `FontFamily` - sets the Font family for the text inside the token.

* `BackgroundColor` - sets the background color of the token.

* `SelectedBackgroundColor` - sets the background color of the token when it is selected.

* `IsCloseButtonVisible` - Enables and disables the close button inside SfAutoComplete.

* `DeleteButtonColor` - sets the color of the close button inside SfAutoComplete.
token.
* `CornerRadius` - sets the corner radius for the token.


{% tabs %}

{% highlight C# %}
	
<<<<<<< HEAD
	public class Employee
    {
        public string Name { get; set; }
        public string Image { get; set; }
        public Employee(string name, string image)
        {
            this.Name = name;
            this.Image = image;

        }
    }

	ObservableCollection<Employee> employeeDetails;

	LinearLayout linearLayout = new LinearLayout(this);
            linearLayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
            linearLayout.SetBackgroundColor(Android.Graphics.Color.White);


            SfAutoComplete employeeAutoComplete = new SfAutoComplete(this);
            employeeAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);
 
            employeeDetails = new ObservableCollection<Employee>();
            employeeDetails.Add(new Employee("Jack", "a0.png"));
            employeeDetails.Add(new Employee("John", "a1.png"));
            employeeDetails.Add(new Employee("James", "a2.png"));
            employeeDetails.Add(new Employee("Jacob", "a3.png"));
            employeeDetails.Add(new Employee("Joy", "a4.png"));
            employeeDetails.Add(new Employee("Victoria", "a5.png"));

            employeeAutoComplete.DisplayMemberPath = "Name";
            employeeAutoComplete.hei
            employeeAutoComplete.DataSource = employeeDetails;
            employeeAutoComplete.MultiSelectMode = MultiSelectMode.Token;
            employeeAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
            employeeAutoComplete.MaximumDropDownHeight = 200;
            employeeAutoComplete.DropDownItemHeight = 50;
            employeeAutoComplete.ImageMemberPath = "Image";
            employeeAutoComplete.TokensWrapMode = TokensWrapMode.Wrap;


            TokenSettings token = new TokenSettings();
            token.BackgroundColor = Color.ParseColor("#f5ffbe");
            token.TextSize = 16;
            token.TextColor = Color.Red;
            token.SelectedBackgroundColor = Color.ParseColor("#ffffe0");
            token.DeleteButtonColor = Color.Brown;
            token.IsCloseButtonVisible = true;
            token.CornerRadius = 15;
            employeeAutoComplete.TokenSettings = token;
            linearLayout.AddView(employeeAutoComplete);
            SetContentView(linearLayout);
 
=======
	public class Student
	{
		string Name;
		string Image;
		public Student(string name,string image)
		{
			this.Name = name;
			this.Image = image;

		}
		public string getName()
		{
			return Name;
		}
		public string getImage()
		{
			return Image;
		}
	}
	
public NSMutableArray StudentDetails
		{
			get;
			set;
		}

		void GetStudentData()
		{
			NSMutableArray array = new NSMutableArray();
			array.Add(getDictionary("John", "image1.png"));
			array.Add(getDictionary("James", "image2.png"));
			array.Add(getDictionary("Jacob", "image33.png"));
			array.Add(getDictionary("Joy", "image4.png"));
			array.Add(getDictionary("Victoria", "image5.png"));
			array.Add(getDictionary("James", "image6.png"));
			StudentDetails = array;
		}

		NSDictionary getDictionary(string name, string image)
		{

			object[] objects = new object[2];
			object[] keys = new object[2];
			keys.SetValue("Name", 0);
			keys.SetValue("Image", 1);
			objects.SetValue((NSString)name, 0);
			objects.SetValue((NSString)image, 1);
			return NSDictionary.FromObjectsAndKeys(objects, keys);
		}
	 
	
	ArrayAdapter<Object> arrayDataAdapters = new ArrayAdapter<Object>(context,Android.Resource.Layout.SimpleListItem1, array);
	StudentDetails.MultiSelectMode=MultiSelectMode.Token;
	studentAutoComplete.DataSource = arrayDataAdapters;

	// Token Customization

	TokensSetting token = new TokensSetting();
	token.FontSize=15;
	token.CornerRadius=5;
	token.SetTextColor(Color.Red);
	token.SetBackgroundColor(Color.Gray);
	token.SelectedBackgroundColor(Color.Yellow);
	token.SetDeleteButtonColor(Color.Maroon);
    token.IsCloseButtonVisible=true;
	StudentDetails.TokensSetting= token;

>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
	 
{% endhighlight %}

{% endtabs %}


	
![](images/TokenRepresentation.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. We can set delimiter character with the `Delimiter` property.

{% tabs %}

{% highlight C# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Andorra");
	countryList.Add ("Akrotiri");
	countryList.Add ("Angola");
	countryList.Add ("Algeria");
	countryList.Add ("Argentina");
	countryList.Add ("Antarctica");
	countryList.Add ("Armenia");
	countryList.Add ("Aruba");
<<<<<<< HEAD
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this,Android.Resource.Layout.SimpleListItem1, countryList);
    countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
=======
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(context,Android.Resource.Layout.SimpleListItem1, countryList);
	countryAutoComplete.SetAutoCompleteSource(countryListDataAdapters);
>>>>>>> a1bddc8d8a9e60b257759106021bfa6c9492311a
	countryAutoComplete.SuggestionMode=SuggestionMode.Contains;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
	countryAutoComplete.Delimiter="#";
	 
{% endhighlight %}

{% endtabs %}
	
![](images/delimiter.png)
	




