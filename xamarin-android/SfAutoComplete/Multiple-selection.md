---
layout: post
title: Multiple Selection in Xamarin.Android SfAutoComplete | Syncfusion®
description: Learn how to select multiple items in Syncfusion® Essential® Xamarin.Android SfAutoComplete Control, its elements, and more.
platform: Xamarin.Android
control: SfAutoComplete
documentation: ug
---

# Multiple Selection in Xamarin.Android SfAutoComplete

You can select multiple items from a suggestion list. There are two ways to perform multiple selection in AutoComplete:

* Token Representation

* Delimiter

## Token Representation

Selected items will be displayed with customizable token representation, and users can remove each tokenized item using the close button.

### Wrap Mode of Tokens

Selected items can be displayed as tokens inside SfAutoComplete in two ways:

* `Wrap` - When `TokensWrapMode` is set to `Wrap`, the selected items will wrap to the next line of the SfAutoComplete.
* `None` - When `TokensWrapMode` is set to `None`, the selected items will be displayed in horizontal orientation.

{% tabs %}

{% highlight C# %}

// Create a class which holds the data source data
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

//Create a new Linear Layout
LinearLayout linearLayout = new LinearLayout(this);
linearLayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
linearLayout.SetBackgroundColor(Android.Graphics.Color.White);
SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

//Crete the data source
ObservableCollection<Employee> employeeDetails = new ObservableCollection<Employee>();
employeeDetails.Add(new Employee("Jack", "jack.png"));
employeeDetails.Add(new Employee("John", "john.png"));
employeeDetails.Add(new Employee("James", "james.png"));
employeeDetails.Add(new Employee("Jacob", "jacob.png"));
employeeDetails.Add(new Employee("Joy", "joy.png"));

//To display the Name, set the DisplayMemberPath
countryAutoComplete.DisplayMemberPath = "Name";

//To display the Image, set the ImageMemberPath
countryAutoComplete.ImageMemberPath = "Image";

//Add the data source
countryAutoComplete.DataSource = employeeDetails;

//Set the MultiSelectMode
countryAutoComplete.MultiSelectMode = MultiSelectMode.Token;
countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
countryAutoComplete.MaximumDropDownHeight = 200;
countryAutoComplete.DropDownItemHeight = 50;

//Set the TokensWrapMode
countryAutoComplete.TokensWrapMode = TokensWrapMode.Wrap;

//Add the SfAutoComplete view to the linear layout
linearLayout.AddView(countryAutoComplete);
SetContentView(linearLayout);

	
{% endhighlight %}

{% endtabs %}

![Xamarin.Android SfAutoComplete token representation](images/TokenRepresentationWrap.png)

### Token Customization

Tokens can be customized in various ways. The available customization options are as follows:
* `TextColor` - Sets the color of the text inside the token.
* `FontSize` - Sets the size of the font inside the token.
* `FontFamily` - Sets the font family for the text inside the token.
* `BackgroundColor` - Sets the background color of the token.
* `SelectedBackgroundColor` - Sets the background color of the token when it is selected.
* `IsCloseButtonVisible` - Enables and disables the close button inside the token.
* `DeleteButtonColor` - Sets the color of the close button inside the token.
* `CornerRadius` - Sets the corner radius for the token.

{% tabs %}

{% highlight C# %}

//Create an object to do Token Customization 
TokenSettings token = new TokenSettings();
token.BackgroundColor = Color.ParseColor("#66ccff");
token.TextSize = 16;
token.TextColor = Color.White;
token.SelectedBackgroundColor = Color.ParseColor("#ffffe0");
token.DeleteButtonColor = Color.Brown;
token.IsCloseButtonVisible = true;
token.CornerRadius = 15;
employeeAutoComplete.TokenSettings = token;
	 
{% endhighlight %}

{% endtabs %}

![Xamarin.Android SfAutoComplete Token Customization](images/TokenRepresentation.png)

## Delimiter

When selecting multiple items, the selected items can be separated using a desired delimiter character. You can set the delimiter character using the `Delimiter` property.

{% tabs %}

{% highlight C# %}

//Set the MultiSelectMode
countryAutoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
countryAutoComplete.Delimiter="#";
	 
{% endhighlight %}

{% endtabs %}
	
![Xamarin.Android SfAutoComplete Delimiter](images/delimiter.png)
	





