---
layout: post
title: Xamarin.Android NuGet Packages | Syncfusion®
description: Learn here about the NuGet Packages and how they can be used to automatically add files and references to your Visual Studio projects.
platform: xamarin.android
control: NuGet Packages
documentation: ug
---

# NuGet Packages Overview

[NuGet](https://www.nuget.org/) can be used to automatically add files and references to your Visual Studio projects. You can use the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages without installing the Essential Studio<sup>®</sup> or Xamarin platform installation to development with the Syncfusion<sup>®</sup> Xamarin.Android controls. From v15.4.0.17 onwards, the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages are published in [nuget.org](https://www.nuget.org/profiles/SyncfusionInc). 

N> Starting from v17.1.0.32 (2018 Volume 1), Syncfusion<sup>®</sup> will no longer publish NuGet packages at [nuget.syncfusion.com](https://nuget.syncfusion.com/).

## Installing NuGet Packages

### Using NuGet Package Manager

The NuGet Package Manager can be used to search and install NuGet packages in the Visual Studio solution or project:

1.	Right-click the project or solution in the Solution Explorer tab, and choose **Manage NuGet Packages…** 

    ![NuGet package manager add-in for Windows](NuGet_Packages_Images/img6.png)

    Alternatively, click **Tools** menu, `NuGet Package Manager | Manage NuGet Packages for Solution...`

2.	By default, the NuGet.org package is selected in the **Package source** drop-down. If NuGet.org is not configured in your Visual Studio, refer to the [Microsoft docs](https://docs.microsoft.com/en-us/nuget/tools/package-manager-ui#package-sources) to configure NuGet.org feed URL in your Visual Studio.

     ![NuGet package manager dialog window](NuGet_Packages_Images/img7.png)               

3.	The Syncfusion<sup>®</sup> Xamarin.Android NuGet Packages are listed and available in the package source feed URL. Search and install the required packages in your application, by clicking **Install** button.

N> The Syncfusion<sup>®</sup> NuGet packages are published in public [NuGet.org](https://www.nuget.org/) from v16.2.0.46. So, If you need to Install earlier version of 16.2.0.46 Syncfusion<sup>®</sup> NuGet packages, [configure Syncfusion<sup>®</sup> private feed URL](https://help.syncfusion.com/xamarin-android/nuget-packages#syncfusion-nuget-feed-url-configuration).


### Using Package Manager Console

To reference the Syncfusion<sup>®</sup> Xamarin.Android component using the Package Manager Console as NuGet packages, follow the below steps.

1.	On the **Tools** menu, select **NuGet Package Manager**, and then **Package Manager Console**. 

2.	Run the following NuGet installation commands. 

    ~~~
    #install specified package in default project
    Install-Package <Package Name>

    #install specified package in specified project 
    Install-Package <Package Name> - ProjectName <Project Name>
    ~~~

    **For example:**

    ~~~
    #install specified package in default project
    Install-Package Syncfusion.Xamarin.SfChart.Android

    #install specified package in specified project 
    Install-Package Syncfusion.Xamarin.SfChart.Android -ProjectName SyncfusionDemoApplication
    ~~~

### Using Visual Studio for macOS

Add packages can be used to search and install NuGet packages to the Visual Studio project in macOS:

1.	Right-click the folder in the project, and then select **Add Packages…** 

    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img8.png)  
              
2.	By default, the NuGet.org package is selected in the **Package source** drop-down.

    ![Add packages dialog](NuGet_Packages_Images/img9.png)  

3.	The NuGet Packages available in the package source location will be listed. Search and install the required packages in your application, by clicking **Add Package** button.

## Managing NuGet package using NuGet CLI

The NuGet Command Line Interface (CLI), nuget.exe, provides the full extent of NuGet functionality to install, create, publish, and manage packages without making any change to the project files.

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command:

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window, and run the following commands to download and install the required NuGet packages to a project specified in the package.config. 

    ~~~
    #install specified package in default project from specified package source for Windows Platform 
    nuget.exe install <Package name | ConfigFilePath > <Options>

    #install specified package in default project from specified package source for MAC/Linux Platform 
    mono nuget.exe install <Package name | ConfigFilePath > <Options>
    ~~~

    N> configPath is optional. This identifies the packages.config or solutions file that lists the packages utilized in the project. 

    **For example:**

    ~~~
    #install specific package for windows 
    nuget.exe install “Syncfusion.Xamarin.Calculate.Android”

    #install all package which mention in package.config path for windows 
    nuget.exe install “C:\Users\SyncfusionApplication\package.config”

    #install specific package for Mac and Linux 
    mono nuget.exe install “Syncfusion.Xamarin.Calculate.Android”

    #install all package which mention in package.config path for Mac and Linux 
    mono nuget.exe install “C:\Users\SyncfusionApplication\package.config”
    ~~~

N> If you need to Install earlier version of 16.2.0.46 Syncfusion NuGet packages, [configure Syncfusion<sup>®</sup> private feed URL](https://help.syncfusion.com/xamarin-android/nuget-packages#syncfusion-nuget-feed-url-configuration).

## Upgrading NuGet packages

### Using NuGet Package Manager 

NuGet packages can be updated to their specific version or latest version available in the Visual Studio solution or project:

1. Right-click the project or solution in the Solution Explorer tab, and choose **Manage NuGet Packages…**
   Alternatively, click **Tools** menu, `NuGet Package Manager | Manage NuGet Packages for Solution...`

2. Select the **Updates** tab to see the packages available for update from the desired package sources. Select the required packages and the specific version from the dropdown, and click the **Update** button.

### Using Visual Studio for macOS

Using **Update** context menu from Visual Studio for Mac application, NuGet packages can be updated:

1.	Right-click the Packages folder in the project, and select **Update**. 

    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img10.png) 

2.	This will update the NuGet package to the latest version. You can double-click Add packages and choose the specific version.

N> To update all the projects from solution, use update option in the solution level. 

### Using Package Manager Console

To update the installed Syncfusion<sup>®</sup> Xamarin.Android NuGet packages using the Package Manager Console, follow the below steps. 

1.	On the **Tools** menu, select **NuGet Package Manager**, and then **Package Manager Console.** 

2.	Run the following NuGet installation commands.

    ~~~ 
    #Update specific NuGet package in default project
    Update-Package <Package Name>

    #Update all the packages in default project
    Update-Package 

    #Update specified package in specified project 
    Update-Package <Package Name> - ProjectName <Project Name>
    ~~~

    **For example:**

    ~~~
    #Update specified Syncfusion<sup>®</sup> Xamarin.Android NuGet package 
    Update-Package Syncfusion.Xamarin.Calculate.Android

    #Update specified package in specified project 
    Update-Package Syncfusion.Xamarin.Calculate.Android -ProjectName SyncfusionDemoApplication
    ~~~

### Using NuGet CLI

Using the NuGet CLI, all the NuGet packages in the project can be updated to the available latest version: 

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command. 

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window. Run the following “update commands” to update the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages.

    ~~~ 
    #update all NuGet packages from config file
    nuget update <configPath> [options]

    #update all NuGet packages
    nuget update
    ~~~      

    N> configPath is optional. This identifies the packages.config or solutions file lists the packages utilized in the project. 
	
    **For example:**

    ~~~          
    #update all NuGet packages from config file
    nuget update “C:\Users\SyncfusionApplication\package.config”
    ~~~

    N> Update command is not working as expected in Mono (Mac and Linux) and projects using PackageReference format.
   
## Syncfusion<sup>®</sup> NuGet feed URL Configuration

### Get the Syncfusion<sup>®</sup> NuGet feed URL 

NuGet Gallery site feed link is configured, by default in your Visual Studio package configuration. If it is not configured, use the NuGet Gallery site feed URL in your Visual Studio: [https://api.nuget.org/v3/index.json](https://api.nuget.org/v3/index.json).

### Syncfusion<sup>®</sup> private site NuGet feed URL 

You should get the private Syncfusion<sup>®</sup> Xamarin NuGet feed URL to install or upgrade the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages. To get the URL from Syncfusion<sup>®</sup> website use the following steps:

1. Navigate to [nuget.syncfusion.com](https://nuget.syncfusion.com/), and select the **MOBILE** tab.     

2. Click the Copy URL label under Xamarin platform to copy the Syncfusion<sup>®</sup> Xamarin platform NuGet feed to clipboard or directly use the following URL: 

    [https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin](https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin) 

    ![Syncfusion Xamarin Android NuGet feed URL](NuGet_Packages_Images/img1.png)

3. Now, use this NuGet feed URL to access the Syncfusion<sup>®</sup> NuGet Packages in Visual Studio. 

### Add the Syncfusion<sup>®</sup> NuGet feed URL

#### Windows

1.	Open your Visual Studio application. 

2.	On the **Tools** menu, select **Options**.

3.	Expand the **NuGet Package Manager** and select **Package Sources**.

4.	Click the **Add** button (green plus), and enter the ‘Package Name’ and ‘Package Source URL’ of the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages.
    
    **Name:** Name of the package listed in the available package sources.
    
    **Source:** Syncfusion<sup>®</sup> Xamarin NuGet Feed URL      
    [https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin](https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin).

5.	Click the **Update** button to add the name and source details to package sources. 

    ![NuGet Package Manager dialog with Syncfusion<sup>®</sup> Xamarin NuGet feed URL for reference](NuGet_Packages_Images/img2.png)

#### macOS 

1.	Open your Visual Studio application. 

2.	Right-click the Packages folder in the project, and then select **Add Packages…**
 
    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img3.png)

3.	Choose the **Configure Sources…** from the dropdown that appears in the left corner of the Add Packages dialog. 

    ![Add packages dialog to choose the Configure Sources](NuGet_Packages_Images/img4.png)

4.	At the bottom right corner of the dialog, click the **Add** button to enter the feed name and the URL. 

    **Name:** Enter the name (For e.g., Syncfusion Xamarin Packages).

    **Location:** Enter the following URL – [https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin](https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin).

    ![Add Package Source dialog to add Syncfusion<sup>®</sup> NuGet feed](NuGet_Packages_Images/img5.png)
 
5.	Now, click **Add Source** and then click **OK**.

#### NuGet CLI 

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command.

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window, and run the following commands to configure the Syncfusion<sup>®</sup> Xamarin.Android NuGet packages. 

    ~~~
    #Add specified package source in NuGet.config file for Windows platform
    nuget.exe Sources Add –Name <Source name> –Source <Source location>

    #Add specified Package Source in Nuget.config file for MAC/Linux platform
    mono nuget.exe Sources Add –Name <Source name> –Source <Source location>
    ~~~

    **For example:**

    ~~~
    #For Windows platform
    nuget.exe Sources Add –Name “Syncfusion Source” –Source “https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin”

    #For MAC/Linux platform
    mono nuget.exe Sources Add –Name “Syncfusion Source” –Source “https://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin”
    ~~~

