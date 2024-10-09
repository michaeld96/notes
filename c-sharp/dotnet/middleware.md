# Middleware

## Definition
Middleware handles HTTP requests or responses. 

Middleware can: 
1. Handle an incoming HTTP request by generating an HTTP response.
2. Process an incoming HTTP request, modify it, and pass it on to 
another piece of middleware.
3. Process an outgoing HTTP response, modify it, and pass it on to 
another piece of middleware or to the ASP.NET Core web server.

## Functions/Classes
* `DeveloperExceptionPageMiddleware` - Provides quick error feedback when building an application.

* `ExceptionHandlerMiddleware` - Provides a generic error page in production so that you don't leak sensitive details.

* `EndpointMiddleware` - Normally generates all HTML and JSON responses.

