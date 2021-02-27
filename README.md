# Disclaimer

Disclaimer: This presentation is for educational purposes only. 

# htfyfb

I have tried and I can't find my first bug 

What should I even do first?

What should I look for?

This is normal because testing is not an easy road but we can improve our chances!

## What we need is:

### An idea of how the internet works

Web applications are interactive applications that run on web browsers. Web applications usually adopt a client-server architecture to run and handle interactions. They typically have front-end components (i.e., the website interface, or "what the user sees") that run on the client-side (browser) and other back-end components (web application source code) that run on the server-side (back end server/databases).

In the past, we interacted with websites that are static and cannot be changed in real-time. This means that traditional websites were statically created to represent specific information, and this information would not change with our interaction. To change the website's content, the corresponding page has to be edited by the developers manually. These types of static pages do not contain functions and, therefore, do not produce real-time changes. That type of website is also known as Web 1.0.
On the other hand, most websites run web applications, or Web 2.0 presenting dynamic content based on user interaction. Another significant difference is that web applications are fully functional and can perform various functionalities for the end-user, while websites lack this type of functionality. Other key differences between traditional websites and web applications include: Being modular Running on any display size Running on any platform without being optimized

#### Web Application Infrastructure

Web applications can use many different infrastructure setups. These are also called models. The most common ones can be grouped into the following four types:


- Client-Server
- One Server
- Many Servers - One Database
- Many Servers - Many Databases


#### Front End

The front end of a web application contains the user's components directly through their web browser (client-side). These components make up the source code of the web page we view when visiting a web application and usually include HTML, CSS, and JavaScript, which are then interpreted in real-time by our browsers.

#### HTML Example 

```
Example <p><strong>Welcome to OWASP Kyiv Meetup</strong><strong></strong></p>
<p></p>
<p><em>This is some italic text.</em></p>
<p></p>
<p><span style="color: #0000ff;">This is some blue text.</span></p>
<p></p>
<p></p>
```

#### Back End

The back end of a web application drives all of the core web application functionalities, all of which is executed at the back end server, which processes everything required for the web application to run correctly. It is the part we may never see or directly interact with, but a website is just a collection of static web pages without a back end.

##### There are four main back end components for web applications:

- Back end Servers 	The hardware and operating system that hosts all other components and is usually run on operating systems like Linux, Windows, or using Containers.
- Web Servers 	Web servers handle HTTP requests and connections. Some examples are Apache, NGINX, and IIS.
- Databases 	(DBs) store and retrieve the web application data. Some examples of relational databases are MySQL, MSSQL, Oracle, PostgreSQL, while examples of non-relational databases include NoSQL and MongoDB.
- Development Frameworks 	Development Frameworks are used to develop the core Web Application. Some well-known frameworks include PHP, C#, Java, Python, and NodeJS JavaScript.

#### DNS Basic

A domain name is a website’s address on the internet. It helps your web browser find the web page you are looking for.

What is a domain name?

Every domain name consists of at least two parts: The TLD (Top Level Domain) and the actual domain known as the SLD (second-level domain). The SLD is also known as the apex domain, root domain, and base domain.

For your web browser to display a web page it needs to translate the domain name into something called an IP address.

Every device connected to the internet has an IP address. An IP address looks something like this 54.126.223.72

For your web browser to find the IP address there could be 5 different places to check:

- Locally on the device
- Resolver server
- Root server
- TLD server
- Authoritative nameserver

The process of finding the IP address is called the Domain Name System (DNS) and this is how it works.

#### HTTP Basic

HTTP (HyperText Transfer Protocol) is an application-level protocol used to access resources over the World Wide Web. The term hypertext stands for text containing links to other resources and text that can be easily interpreted by the readers.

HTTP communication consists of a client and a server, where the client requests the server for a resource. The server processes the requests and returns the requested resource. The default port for HTTP communication is 80; however, this can be changed.

Resources over HTTP are accessed via a Uniform Resource Locator (URL). Let's look at the structure of a URL.

scheme://[user:password@]domain:port/path?query_string#fragment_id

##### Component details:

- The scheme, which in many cases is the name of a protocol (but not always), defines how the resource will be obtained. Examples include HTTP, HTTPS, FTP, file, and many others. Although schemes are case-insensitive, the canonical form is lowercase.

- User info this is an optional component that contains credentials in the form username:password, which is used to authenticate to the host.

- The domain name or literal numeric IP address gives the destination location for the URL. A literal numeric IPv6 address may be given, but must be enclosed in [ ] e.g.[db8:0cec::99:123a].

The domain google.com, or its numeric IP address 173.194.34.5, is the address of Google’s website.

The domain name portion of a URL is not case sensitive since DNS ignores case:

http://en.example.org/ and HTTP://EN.EXAMPLE.ORG/ both open the same page.

- The port number, given in decimal, is optional; if omitted, the default for the scheme is used.

For example, http://vnc.example.com:5800 connects to port 5800 of vnc.example.com, which may be appropriate for a VNC remote control session. If the port number is omitted for an HTTP: URL, the browser will connect on port 80, the default HTTP port. The default port for an HTTPS: request is 443.

- The path is used to specify and perhaps find the resource requested. This path may or may not describe folders on the file system in the webserver. It may be very different from the arrangement of folders on the webserver. It is case-sensitive, though it may be treated as case-insensitive by some servers, especially those based on Microsoft Windows.

If the server is case sensitive and http://en.example.org/wiki/URL is correct, then http://en.example.org/WIKI/URL or http://en.example.org/wiki/url will display an HTTP 404 error page, unless these URLs point to valid resources themselves.

- The query string contains data to be passed to software running on the server. It may contain name/value pairs separated by ampersands, for example

?first_name=John&last_name=Doe.

- The fragment identifier, if present, specifies a part or a position within the overall resource or document.

When used with HTML, it usually specifies a section or location within the page and is used in combination with Anchor elements or the “id” attribute of an element, the browser is scrolled to display that part of the page.


##### Request 

`https://www.bugbountytraining.com/FFHv2/#book`

```
GET /FFHv2/ HTTP/1.1
Host: www.bugbountytraining.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
```

The first line of an HTTP request contains three fields separated by spaces.

- Method 	The first field stands for the HTTP method or verb, which specifies the type of action to perform.
- Path 	The second field is the path to the resource being accessed. This field can also be suffixed with a query string.
- Version 	The third and final field is used to denote the HTTP version.

The next set of lines contain HTTP header value pairs. These are used to specify various attributes of a request. The headers are terminated with a new line, which is necessary for the server to validate the request. This can be followed by the request body, which we will analyze in later.


##### Response

```
HTTP/1.1 200 OK
Server: nginx/1.18.0 (Ubuntu)
Date: Fri, 26 Feb 2021 23:54:53 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Content-Length: 20657


<!DOCTYPE html>
<html lang="en">
  <head>
    <title>
```
##### Commonly Used HTTP Methods

Multiple HTTP methods can be used while accessing resources. Let's look at some of the commonly used methods.

- GET 	This is the most common HTTP method, which requests a specific resource. Additional data can be passed to the server via query strings.
- POST 	This is another common method used to send data to the server. It can handle multiple types of input, such as text, PDFs, and other forms of binary data. This data is appended in the request body present after the headers. The POST method is commonly used when sending information (forms, logins) or uploading data to a website, such as images or documents.
- HEAD 	This method requests the headers that would be returned if a GET request was made to the server. It doesn't return the request body and is usually made to check the response length before downloading resources.
- PUT 	This method is similar to POST, as it's used to create new resources on the server. Allowing this method without proper controls can lead to the addition of malicious resources (i.e., uploading a malicious file to the webserver).
- DELETE 	This method lets users delete an existing resource on the webserver. It can lead to Denial of Service (DoS) without proper controls in place.
- OPTIONS 	This method returns information about the server, such as the methods accepted by it.

The list above highlights only a few methods. The availability of a particular method depends on the server as well as the application configuration.

##### An HTTP server can return five types of response codes:

- 1xx 	Usually provides information and continues processing the request.
- 2xx 	Positive response codes are returned when a request succeeds.
- 3xx 	Returned when the server redirects the client.
- 4xx 	This class of codes signifies improper requests from the client. For example, requesting a resource that doesn't exist or requesting a bad format.
- 5xx 	Returned when there is some problem with the HTTP server itself.

Let's look at some common HTTP response codes and their meaning.

- 200 OK 	Returned on a successful request, and the response usually contains the requested resource.
- 302 Found 	This code redirects the client to another URL. For example, redirecting the user to their dashboard after a successful login.
- 400 Bad Request 	Usually returned on encountering malformed requests such as requests with missing line terminators.
- 403 Forbidden 	This code signifies that the client doesn't have appropriate access to the resource. It can also be returned when the server detects malicious input from the user.
- 500 Internal Server Error 	As the name describes, this code is returned when the server cannot process the request.

### Set up testing environment right

Tools like FFUF, Amass, Nuclei are good but you should learn how to use them well
 
#### Browser:

Сertainly need to be installed

- Wappalyzer

- FoxyProxy

Also look at:

- Multi-Account Containers

- Open Multiple URL

- Shodan 

- WHOIS

- PwnFox

- Cookie Editor
	
#### DevTools

- Page Inspector View and edit page content and layout. Visualize many aspects of the page including the box model, animations, and grid layouts.

- Web Console See messages logged by a web page and interact with the page using JavaScript.

- JavaScript Debugger Stop, step through, examine, and modify the JavaScript running on a page.

- Network Monitor See the network requests made when a page is loaded.

- Performance Tools Analyze your site's general responsiveness, JavaScript, and layout performance.

- Responsive Design Mode See how your website or app will look and behave on different devices and network types.

- Accessibility inspector Provides a means to access the page's accessibility tree, allowing you to check what's missing or otherwise needs attention.

- Application panel Provides tools for inspecting and debugging modern web apps (also known as Progressive Web Apps). This includes inspection of service workers and web app manifests.

#### Proxy

Get OWASP ZAP or Burp or any other proxy your prefer. Set it, add extensions, see more.

### Flow

An idea of the kind of bugs you can find

Having a method will help you to organize your thoughts and ensure you won't miss anything

You don't need to  be an expert to  find your first bug

Before we start to test the assets we need to learn what for it.
We should be able to answer the question what does this app do?
Does it have a database?
Is this using an API?

Try to become more familiar with the app and figure out what bugs are likely there on a regular program flow

When you test a website you should be thinking about the features

Registration? Register a user, even multiple for BAC testing
Buying a product? Put it in your cart and follow the checkout process
You are not necessarily lucky to test all different endpoints, but you should try to test  all features that are in front of you

#### To map the application 

Use proxy such as Burp  OWASP ZAP

Press all the buttons

Fuzz it

You want to get all the endpoints the app has

You should be able to map high-level functions to endpoints 

#### Focus on the SIGNS of bugs:

Reflecting output -> XSS

Client side validation -> SQLi

IDs -> IDORs

Redirect possibility -> Open Redirect 

Absence of anti-CSRF tokens -> CSRF

The route to file -> LFD

URL as an input -> SSRF

XML in request -> XXE 

File Uploads -> RCE

A lot of roles, complex logic -> Business logic bugs















