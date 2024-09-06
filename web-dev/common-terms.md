# Definition of Common Terms in Web Development

## Endpoints

Endpoints are physical devices that are connected to a computer network
that can exchange information with one another. Some examples of these
physical devices are servers, smart-phones, virtual machines, etc.

## HTTP

HTTP stands for Hyper Text Transfer Protocol. This is a stateless
request-response cycle. This works usually a client sending a request to
a server, and then this serve sends a response back to the client.

Every HTTP request consists of a verb indicating the type of the request
and a path indicating the resource to interact with. A request usually 
includes headers, which are key-value pairs, and some cases a includes
a body, such as the contents of a form when sending data to a server.

### HTTP Request Example
This is the syntax for request:
```http
<VERB> <path>
<header-key-1>: <header-val-1>
<header-key-2>: <header-val-2>
<optional-body>
```

Here is an example:
```http
curl -v miketdick.com
GET / HTTP/2
Host: miketdick.com
User-Agent: curl/8.7.1
Accept: */*
```

### HTTP Response Example:
A response contains:
* a status line
* zero or more response headers
* an empty line
* message body (optional)

```http
HTTP/2 200 
server: GitHub.com
 content-type: text/html; charset=utf-8
 last-modified: Tue, 06 Aug 2024 03:46:47 GMT
 access-control-allow-origin: *
 etag: "66b19ca7-8e7"
 expires: Fri, 06 Sep 2024 18:25:33 GMT
 cache-control: max-age=600
 x-proxy-cache: MISS
 x-github-request-id: 0EB8:7FAD7:E8A396:FF7054:66DB46C5
 accept-ranges: bytes
 age: 339
 date: Fri, 06 Sep 2024 18:21:13 GMT
 via: 1.1 varnish
 x-served-by: cache-dtw8029-DTW
 x-cache: HIT
 x-cache-hits: 0
 x-timer: S1725646873.274758,VS0,VE1
 vary: Accept-Encoding
 x-fastly-request-id: d69b1fc5df55465299ef04a5c72df9618f31da00
 content-length: 2279
 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/indexstyle.css">
    <link rel = "stylesheet" href = "css/common.css">
    <!--- Below is used for Font Awesome. --->
	<script src="https://kit.fontawesome.com/4c4bda27d1.js" crossorigin="anonymous"></script>
    <link rel = "shortcut icon" type="image/png" href="imgs/favicon.png"/>
    <link rel="icon" href="imgs/initials.png">
    <title>Michael Dick's Website</title>
</head>
<body>
    <div id="navbar"></div>
    <div class = "content">
    <div class="me-section">
        <img src="imgs/me.jpeg" alt="Picture of Michael Dick">
        <div class="bio">
            <h2>Biography</h2>
            <p>Hi there! My name is Michael Dick and I am currently a computer science major and 
            mathematics minor at the University of Michigan. My interests are web development, 
            computer graphics, and mathematical geometry. Languages I am familiar with are: 
            Python, C++, HTML5, CSS3, and JavaScript. A little bit about me is that 
            I love analog photography, hiking in the forest or the desert, and writing short 
            stories. Feel free to contact me by hitting “Contact” on the navigation bar 
            and will respond as soon as possible. Enjoy the site!</p>
        </div>
    </div>
    <div class="grey-line"></div>
    <div class="graphic-nav">
        <a href="html/resume.html" class = "gra grow">
            <p class = "title">Resume</p>
            <p class = "icon"><i class="far fa-copy"></i></p>
        </a>
        <a href="html/projects.html"class = "gra grow">
            <p class = "title">Projects</p>
            <p class = "projects-icon"><i class="fas fa-code"></i></p>
        </a>
        <a href="html/contact.html" class = "gra grow">
            <p class = "title">Contact</p>
            <p class = "icon"><i class="far fa-paper-plane"></i></p>
        </a>
    </div>
</div>
    <div id="footer"></div>
</body>
<script src = "js/indexjs.js"></script>
<script src = "js/navbar-loader.js"></script>
<script src = "js/footer-loader.js"></script>
* Connection #0 to host miketdick.com left intact
</html>
```
## REST

REST stands for representational state transfer. RESTful applications 
typically use lightweight and stateless HTTP calls to read, post, and 
delete data.
