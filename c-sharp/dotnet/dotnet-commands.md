# Dotnet Commands

## `dotnet restore`

This command restores project dependencies by downloading them from
NuGet package manager.

The dependencies are in the `.csproj` file.

## `dotnet build`

This command restores and compiles the app by default. Can include
`-no-restore` to not have the restore happen.

## `dotnet run`

This restores and runs the app by default.

## `dotnet new web -o <project-name>`

Creates an empty ASP.NET Core Empty project.

# `sln` 

## `dotnet new sln -n <project-name>`

This will create a solution file named whatever `<project-name>` is.

## `dotnet sln add <project-name>`

Adds the new project to the solution file.


