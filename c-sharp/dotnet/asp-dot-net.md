# ASP.NET

## Web Server

The web server that handles all of the http request is Kestrel. This
handles the raw http requests and constructs an internal representation
of it as `HttpContext` object. When the application wants to respond, it
send this back to Kestrel (the web server) and Kestrel coverts this IR 
(internal representation) back into raw HTTP.

## Intermediate Language

A ASP.NET application is compiled to a intermediate language (IL) that 
is platform-independent. If a platform has .NET runtime installed
then the compiled IL will be ran on that platform.

## Structure: `Program.cs`

This file controls the startup and configuration of the app at runtime

## Structure: `.csproj`

This file contains all the details required to build the project, including NuGet packages used by the project.

## Structure: `appsettings.json` and `appsettings.Development.json`

Both of these files are generated when running the `web` template
when creating a new ASP.NET project. Both of these files provide
configuration settings that are used at runtime to control the behavior
of the app.

## Including NuGet Packages

In your `.csproj` file, this is where you will include NuGet packages
that you want to include. To do this:
1. Add the package inside of the project folder.
```
dotnet add package Newtonsoft.JSON
```
2. Verify that this package is referenced in your project's `.csproj`.
```xml
...
<ItemGroup>
    <PackageReference Include="NewtonSoft.Json" Version="13.0.1" />
</ItemGroup>
...
```