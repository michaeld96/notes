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

## Structure: Middleware

Small components that execute in sequence when the application receives
an HTTP request. They can perform lots of host functions such as logging, identifying the current user for the request, serving static
files, and handling errors.

## Structure: Endpoints

Endpoints define how the response should be generated for a specific
request to a URL the application.

## Structure: Entry Point
The entry point consists of six steps:
1. Create a `WebApplicationBuilder` instance.
2. Register the required services and configurations with `WebApplicationBuilder`.
3. Call `Build()` on the builder instance to create a `WebApplication` instance.
4. Add middleware to the `WebApplication` to create a pipeline.
5. Map the endpoints in the application.
6. Call `Run()` on the `WebApplication` to start the server and handle requests.

```cs
using Microsoft.AspNetCore.HttpLogging;

var builder = WebApplication.CreateBuilder(args); // 1. Create WebApplication instance.
// 2. Start registering services to the web app instance.
builder.Services.AddHttpLogging(opts => 
    opts.LoggingFields = HttpLoggingFields.RequestProperties
);

builder.Logging.AddFilter(
    "Microsoft.AspNetCore.HttpLogging", LogLevel.Information
);

var app = builder.Build(); // 3. Build the instance.

if (app.Environment.IsDevelopment())
{
    app.UseHttpLogging(); // 4. Adding middleware.
}

app.MapGet("/", () => "Hello World!"); // 5. Map endpoints in app.
app.MapGet("/person", () => new Person("Michael", "Dick"));

app.Run(); // 6. Start the application.

public record Person(string FirstName, string LastName);

```

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