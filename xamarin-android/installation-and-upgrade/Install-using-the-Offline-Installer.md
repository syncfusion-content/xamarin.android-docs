---
layout: post
title: Syncfusion Essential Studio Offline Installer
description: this section provides information regarding the Syncfusion Xamarin Offline installer and steps for installing it
platform: Xamarin
control: Installation and Deployment
documentation: ug

---

# Installation using Offline Installer

You can refer to the [**Download**](https://help.syncfusion.com/xamarin/installation-and-upgrade/download) section to learn how to get the Xamarin trial or licensed installer.

## Installing with UI   

The steps below show how to install the Essential Studio Xamarin product.

1.	Open the Syncfusion Xamarin offline installer file from downloaded location by double-clicking it. The Installer Wizard automatically opens and extracts the package

    ![Installer extraction wizard](Platform_images/Step-by-Step-Installation_img1.png)

    N> The Installer wizard extracts the syncfusionessentialxamarin_(version).exe dialog, which displays the package's unzip operation.

2.	To unlock the Syncfusion offline installer, you have two options:

   
    * *Login To Install*
   
    * *Use Unlock Key*
   
   
   
    **Login To Install**
   
    You must enter your Syncfusion email address and password. If you don't already have a Syncfusion account, you can sign up for one by clicking **"Create an account"**. If you have forgotten your password, click on **"Forgot Password"** to create a new one. Once you've entered your Syncfusion email and password, click Next.

    ![Login credentials](Platform_images/Step-by-Step-Installation_img2.png)   


    **Use Unlock Key**
   
    Unlock keys are used to unlock the Syncfusion offline installer, and they are product and version specific. You should use either Syncfusion licensed or trial Unlock key to unlock Syncfusion Xamarin installer.
   
    The trial unlock key is only valid for 30 days, and the installer will not accept an expired trial key. 
   
    To learn how to generate an unlock key for both trial and licensed products, see [this](https://www.syncfusion.com/kb/2326) Knowledge Base article.

    ![Product key](Platform_images/Step-by-Step-Installation_img3.png)   


3.	After reading the License Terms and Privacy Policy, check the **“I agree to the License Terms and Privacy Policy”** check box. Click the Next button.


4.	Change the install and sample locations here. You can also change the Additional settings. Click Next\Install to install with the default settings.


    ![Advanced options](Platform_images/Step-by-Step-Installation_img4.png)

    **Additional Settings**
    
	* Select the **Install Demos** check box to install Syncfusion samples, or leave the check box unchecked, if you do not want to install Syncfusion samples.
    * Check the **Create Desktop Shortcut** checkbox to add a desktop shortcut for Syncfusion Control Panel.
    * Check the **Create Start Menu Shortcut** checkbox to add a shortcut to the start menu for Syncfusion Control Panel.




5.	If any previous versions of the current product is installed, the Uninstall Previous Version(s) wizard will be opened. Select **Uninstall** checkbox to uninstall the previous versions and then click the Proceed button.


    ![Advanced options](Platform_images/Step-by-Step-Installation_img7.png)
	
	
	N> From the 2021 Volume 1 release, Syncfusion has added the option to uninstall previous versions from 18.1 while installing the new version.
	
	
	N> If any version is selected to uninstall, a confirmation screen will appear; if continue is selected, the Progress screen will display the uninstall and install progress, respectively. If none of the versions are chosen to be uninstalled, only the installation progress will be displayed.
	
	**Confirmation Alert**
	
	![Confirmation wizard](Platform_images/Step-by-Step-Installation_img8.png)
	
	**Uninstall Progress:**
	
	![Uninstalling wizard](Platform_images/Step-by-Step-Installation_img9.png)
	
	**Install Progress**
	
	![Installing wizard](Platform_images/Step-by-Step-Installation_img5.png)

    N> The Completed screen is displayed once the Xamarin product is installed. If any version is selected to uninstall, The completed screen will display both install and uninstall status.
	
	![Completed wizard](Platform_images/Step-by-Step-Installation_img10.png)
	
7.  After installing, click the **Launch Control Panel** link to open the Syncfusion Control Panel.


8.  Click the Finish button. Your system has been installed with the Syncfusion Essential Studio Xamarin product.

## Installing in silent mode

The Syncfusion Essential Studio Xamarin Installer supports installation and uninstallation via the command line. The sections that follow demonstrate this ability.

### Command Line Installation

To install through the Command Line in Silent mode, follow the steps below.

1.	Run the Syncfusion Flutter installer by double-clicking it. The Installer Wizard automatically opens and extracts the package.
2.	The file syncfusionessentialxamarin_(version).exe file will be extracted into the Temp directory.
3.	Run %temp%. The Temp folder will be opened. The syncfusionessentialxamarin_(version).exe file will be located in one of the folders.
4.	Copy the extracted syncfusionessentialxamarin_(version).exe file in local drive.
5.	Exit the Wizard.
6.	Run Command Prompt in administrator mode and enter the following arguments.

   
    **Arguments:** “Installer file path\SyncfusionEssentialStudio(platform)_(version).exe” /Install silent /PIDKEY:“(product unlock key)” [/log “{Log file path}”] [/InstallPath:{Location to install}] [/InstallSamples:{true/false}] [/InstallAssemblies:{true/false}] [/UninstallExistAssemblies:{true/false}] [/InstallToolbox:{true/false}]


    N> [..] – Arguments inside the square brackets are optional.

    **Example:** “D:\Temp\syncfusionessentialxamarin_x.x.x.x.exe” /Install silent /PIDKEY:“product unlock key” /log “C:\Temp\EssentialStudio_Platform.log” /InstallPath:C:\Syncfusion\x.x.x.x /InstallSamples:true /InstallAssemblies:true /UninstallExistAssemblies:true /InstallToolbox:true

	
7.  Essential Studio for Xamarin is installed.

   N> x.x.x.x should be replaced with the Essential Studio version and the Product Unlock Key needs to be replaced with the Unlock Key for that version.
   

### Command Line Uninstallation

Syncfusion Essential Xamarin can be uninstalled silently using the Command Line.

1.	Run the Syncfusion Flutter installer by double-clicking it. The Installer Wizard automatically opens and extracts the package.
2.	The file syncfusionessentialxamarin_(version).exe file will be extracted into the Temp directory.
3.	Run %temp%. The Temp folder will be opened. The syncfusionessentialxamarin_(version).exe file will be located in one of the folders.
4.	Copy the extracted syncfusionessentialxamarin_(version).exe file in local drive.
5.	Exit the Wizard.
6.	Run Command Prompt in administrator mode and enter the following arguments.

    **Arguments:** “Copied installer file path\syncfusionessentialxamarin_(version).exe” /uninstall silent 

    **Example:** “D:\Temp\syncfusionessentialxamarin_x.x.x.x.exe" /uninstall silent


8.  Essential Studio for Xamarin is uninstalled.
   
   
## Explore the libraries package

The Syncfusion libraries, samples, and NuGet packages can be found installed location.

{Essential Studio installed location}\Syncfusion\Essential Studio\{version}\Xamarin

**Example:** C:\Program Files (x86)\Syncfusion\Essential Studio\Xamarin\19.1.0.54

* **"lib"** directory - e.g., C:\Program Files (x86)\Syncfusion\Essential Studio\Xamarin\19.1.0.54\lib

   It includes all of the libraries needed for the Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.
   
* **"nuget"** directory - e.g., C:\Users\Public\Documents\Syncfusion\Xamarin\19.1.0.54\nuget

   It includes NuGet packages for the Syncfusion libraries. The same NuGet packages can also be configured via nuget.org.
   
* **"sample"** directory - e.g., C:\Users\Public\Documents\Syncfusion\Xamarin\19.1.0.54\sample

   It includes sample applications for our controls in the Xamarin.iOS, Xamarin.Android, and Xamarin.Forms products, which are located in the iOS, Android, and Forms folders, respectively.

The "Forms" directory includes,

* Individual control sample folders: These folders contain samples for individual controls such as SfChart, SfDataGrid, and so on. These samples are light in weight because they represent individual controls. You can check the samples for your required controls on your own faster and with less deployment time.

* “nuget” folder: It contains the compiled assemblies of the above samples as NuGet package. As explained in the following step, it is referred to in the common sample browser.

* “SampleBrowser” folder: It includes a common sample browser that refers to the samples of individual controls as a NuGet package. Run this to view demo samples of all controls in a single application.

* It also includes sample applications such as Patient Monitor, Server Monitor, and Invoice.

### Add reference to the project

The assembly references can then be added to the appropriate projects, such as PCL, XForms.Droid, XForms.iOS, and XForms.UWP. This link will take you to the dependencies for each control.

I> For iOS and UWP projects, an additional step is currently required after adding the reference. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).

I> If the project is built in release mode with the .NET Native tool chain enabled, one more step is required for UWP alone. For example, if we are using SfKanban, you can refer to the [KB article](https://www.syncfusion.com/kb/7170) for more information.