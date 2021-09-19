<table>
  <thead>
    <tr>
      <td align="left">
        :warning:
      </td>
      <td align="left" width="100%">
          <strong>NOTICE</strong>
      </td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2">
          This branch is for the <strong>Umbraco 9</strong> version of this package. For the Umbraco 8 package, see <a href="https://github.com/skybrud/Skybrud.Umbraco.Redirects/tree/v2/latest"><strong>v2/latest</strong></a> branch.
      </td>
    </tr>
  </tbody>
</table>

# Skybrud.Umbraco.Redirects [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md) [![NuGet](https://img.shields.io/nuget/vpre/Skybrud.Umbraco.Redirects.svg)](https://www.nuget.org/packages/Skybrud.Umbraco.Redirects/3.0.0-alpha003) [![NuGet](https://img.shields.io/nuget/dt/Skybrud.Umbraco.Redirects.svg)](https://www.nuget.org/packages/Skybrud.Umbraco.Redirects)

**Skybrud.Umbraco.Redirects** is a redirects manager for Umbraco 9. The package features a dashboard and property editor that let's users manage inbound redirects from within the Umbraco backoffice.

URLs can be added to redirect to either a content item, media item or a custom URL.

## Installation

The Umbraco 9 version of this package is only available via NuGet. To install the package, you can use either .NET CLI:

```
dotnet add package Skybrud.Umbraco.Redirects --version 3.0.0-alpha003
```

or the older NuGet Package Manager:

```
Install-Package Skybrud.Umbraco.Redirects -Version 3.0.0-alpha003
```

**Umbraco 8**  
For the Umbraco 8 version of this package, see the [**v2/latest**](https://github.com/skybrud/Skybrud.Umbraco.Redirects/tree/v2/latest) branch instead.

**Umbraco 7**  
For the Umbraco 7 version of this package, see the [**v1/latest**](https://github.com/skybrud/Skybrud.Umbraco.Redirects/tree/v1/latest) branch instead.






## Features

- Global dashboard for listing all redirects. Supports filtering and searching.

- Property editor that can be added to either a content item or media item to show inbound redirects

- Package only handles custom redirecs - eg. added manually by an editor. The package will let Umbraco 7.5+ handle redirects for renamed pages

- Includes a `RedirectsService` for managing the redirects from your own code

[NuGetPackage]: https://www.nuget.org/packages/Skybrud.Umbraco.Redirects
[GitHubRelease]: https://github.com/skybrud/Skybrud.Umbraco.Redirects/releases



## Screenshots

Besides the dashboard shown in the top of this page, the package also features property editor that let's users add new inbound redirect directly from the content or media item being editied.

For instance the screenshot below illustrates the property editor added to a content type:

![image](https://cloud.githubusercontent.com/assets/3634580/22441953/c3c374fa-e739-11e6-8453-78402e3103fd.png)

Or the same property editor added to a media type - eg. here added to the `Image` media type:

<!--![image](https://cloud.githubusercontent.com/assets/3634580/22441813/3b8045a0-e739-11e6-9182-8011cc9785fb.png)-->
![image](https://cloud.githubusercontent.com/assets/3634580/22441900/8810a022-e739-11e6-858b-4c62d86796ad.png)

## Under the hood

The package comes with a HTTP module that will kick in when Umbraco or IIS returns a response with a 404 status code. If this is the case, the module will look up the requested URL, and then redirect the user if a matching redirect is found in the database.
