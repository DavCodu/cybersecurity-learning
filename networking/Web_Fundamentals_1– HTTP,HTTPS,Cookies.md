Web Fundamentals 1 – HTTP, HTTPS, Cookies
Goal

Understand the basics of HTTP and HTTPS protocols, how requests and responses work, and how cookies are used in web communication.

Topics Covered
HTTP request and response structure
HTTPS and secure communication
HTTP methods: GET, POST
Headers and status codes
Cookies: creation, sending, and storage
Commands / Tools Used
curl – send HTTP requests from terminal
Browser DevTools – inspect requests and responses
wget – download content from HTTP servers
echo & nc – simulate basic HTTP requests (optional)
HTTP Request Example

GET request using curl:

curl -v http://example.com

Output:

> GET / HTTP/1.1
> Host: example.com
> User-Agent: curl/7.68.0

< HTTP/1.1 200 OK
< Content-Type: text/html; charset=UTF-8
< Set-Cookie: sessionid=abc123; Path=/; HttpOnly
HTTPS Request Example
curl -v https://example.com

Notes:

Communication is encrypted via TLS/SSL
Ensures data integrity and confidentiality
Cookies
Cookies store data on the client-side
Sent by server via Set-Cookie header
Returned by client in subsequent requests via Cookie header

Example:

Set-Cookie: sessionid=abc123; Path=/; HttpOnly
Cookie: sessionid=abc123
Inspecting Requests in Browser
Open DevTools → Network tab
Refresh page → view HTTP requests
Check request headers, response headers, cookies

Example Headers:

GET /index.html HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Cookie: sessionid=abc123

HTTP/1.1 200 OK
Content-Type: text/html
Set-Cookie: theme=dark; Path=/; Secure; HttpOnly
Key Takeaways
HTTP = unencrypted protocol
HTTPS = encrypted protocol (TLS/SSL)
Cookies = store session info or preferences
Always check request and response headers to debug or analyze web apps
Platform

Practice completed on TryHackMe – Web Fundamentals 1

Notes / Diagrams

HTTP Request-Response Flow:

Client (Browser) --> HTTP Request --> Server
Server --> HTTP Response --> Client (Browser)

Cookie Flow:

Server sets cookie --> Browser stores cookie --> Browser sends cookie in next request
