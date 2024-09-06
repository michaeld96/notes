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