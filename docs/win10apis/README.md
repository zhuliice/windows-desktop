# Microsoft.Windows.SDK.Contracts

The [Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) NuGet packages are designed to allow you to quickly and easily add the latest Windows 10 Runtime APIs to your .NET libraries and applications.  For the complete list of the APIs, see: [Windows UWP Namespaces](https://docs.microsoft.com/uwp/api/). 

### Requirements

The Microsoft.Windows.SDK.Contracts NuGet packages are designed for .NET Framework 4.6+ or .NET Core 3.0 and only support projects configured using [Package Reference](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files) as their package management format.   

## Getting Started

### Step1 : Configure your project to support [Package Reference](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files):

> [!Information]
> .NET Core and .NET Standard projects already use the `PackageReference` format

#### New Projects

For new projects, follow these steps to configure **NuGet Settings** in Visual Studio 2017 or Visual Studio 2019 to default to PackageReference:

1.	From the Tools menu of Visual Studio, choose **NuGet Package Manager -> Package Manager Settings**.  
2.	Under **Package Management**, make sure the **“Default package management format:”** specifies **PackageReference**.

#### Existing Projects

To change an existing project from Packages.Config to use Package Reference in VS2017, right-click on the Packages.config file and choose 
**Migrate packages.config to Package Reference...**  For more information refer to [Migrate packages config to package reference](https://docs.microsoft.com/en-us/nuget/reference/migrate-packages-config-to-package-reference).

### Step 2: Add the Microsoft.Windows.SDK.Contracts NuGet package to your project

1.	Open the [NuGet Package Manager Console](https://docs.microsoft.com/nuget/tools/package-manager-console) 
2.	Install the package that includes the Windows 10 Contracts you want to target.  Currently the following are supported:


- Windows 10 version 1803
`Install-Package Microsoft.Windows.SDK.Contracts -Version 10.0.17134.1000-preview` 
- Windows 10 version 1809
`Install-Package Microsoft.Windows.SDK.Contracts -Version 10.0.17763.1000-preview`
- Windows 10 version 1903 – preview
 `Install-Package Microsoft.Windows.SDK.Contracts -Version 10.0.18362.2002-preview`



## Get Coding

If you want to try it out, this sample shows how to access the Geolocation APIs with a button click, and output the values to a text box.

```cs
private async void button1_Click_1(object sender, EventArgs e)
{
var locator = new Windows.Devices.Geolocation.Geolocator();
var location = await locator.GetGeopositionAsync();
var position = location.Coordinate.Point.Position;
var latlong = string.Format("lat:{0}, long:{1}", position.Latitude, position.Longitude);
textBox1.Text = latlong;
}
```
## Feedback / Contributions
This repo can be used for the reporting of issues found with the Windows SDK NuGet packages. 

