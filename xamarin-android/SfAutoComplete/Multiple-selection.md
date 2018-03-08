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

### Wrap Mode of Token

The selected item can be displayed as token inside SfAutoComplete in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the SfAutoComplete.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight C# %}

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
            employeeDetails.Add(new Employee("Jack", "jack.png"));
            employeeDetails.Add(new Employee("John", "john.png"));
            employeeDetails.Add(new Employee("James", "james.png"));
            employeeDetails.Add(new Employee("Jacob", "jacob.png"));
            employeeDetails.Add(new Employee("Joy", "joy.png"));
            employeeDetails.Add(new Employee("Victoria", "Victoria.png"));

            employeeAutoComplete.DisplayMemberPath = "Name";
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
	ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this,Android.Resource.Layout.SimpleListItem1, countryList);
    countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
	countryAutoComplete.SuggestionMode=SuggestionMode.Contains;
	countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
	countryAutoComplete.Delimiter="#";
	 
{% endhighlight %}

{% endtabs %}
	
![](images/delimiter.png)
	




