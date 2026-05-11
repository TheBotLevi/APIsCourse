# APIs

`curl` is a command-line tool used to send http/https requests

we can use it to:

- call APIs
- download files
- test servers
- inspect HTTP traffic

`-v` means verbose mode:
tells `curl` to print extra details about what happens internally
to see things like:

- DNS resolution
- TCP connection
- TLS/SSL handshake
- HTTP request headers
- HTTP response headers

`curl -v _URL_`

-- curl -v https://echo.hoppscotch.io

* Host echo.hoppscotch.io:443 was resolved.
* IPv6: 2a05:d014:58f:6200::258, 2a05:d014:58f:6200::259
* IPv4: 63.176.8.218, 35.157.26.135
*   Trying [2a05:d014:58f:6200::258]:443...
* Immediate connect fail for 2a05:d014:58f:6200::258: Network is unreachable
*   Trying [2a05:d014:58f:6200::259]:443...
* Immediate connect fail for 2a05:d014:58f:6200::259: Network is unreachable
*   Trying 63.176.8.218:443...
* ALPN: curl offers h2,http/1.1
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
*  CAfile: /etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem
*  CApath: none
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_128_GCM_SHA256 / x25519 / id-ecPublicKey
* ALPN: server accepted h2
* Server certificate:
*  subject: CN=echo.hoppscotch.io
*  start date: May  5 15:03:45 2026 GMT
*  expire date: Aug  3 15:03:44 2026 GMT
*  subjectAltName: host "echo.hoppscotch.io" matched cert's "echo.hoppscotch.io"
*  issuer: C=US; O=Let's Encrypt; CN=E7
*  SSL certificate verify ok.
*   Certificate level 0: Public key type EC/prime256v1 (256/128 Bits/secBits), signed using ecdsa-with-SHA384
*   Certificate level 1: Public key type EC/secp384r1 (384/192 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 2: Public key type RSA (4096/152 Bits/secBits), signed using sha256WithRSAEncryption
* Connected to echo.hoppscotch.io (63.176.8.218) port 443
* using HTTP/2
* [HTTP/2] [1] OPENED stream for https://echo.hoppscotch.io/
* [HTTP/2] [1] [:method: GET]
* [HTTP/2] [1] [:scheme: https]
* [HTTP/2] [1] [:authority: echo.hoppscotch.io]
* [HTTP/2] [1] [:path: /]
* [HTTP/2] [1] [user-agent: curl/8.15.0]
* [HTTP/2] [1] [accept: */*]
> GET / HTTP/2
> Host: echo.hoppscotch.io
> User-Agent: curl/8.15.0
> Accept: */*
> 
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* Request completely sent off
< HTTP/2 200 
< access-control-allow-credentials: true
< access-control-allow-headers: Origin, X-Requested-With, Content-Type, Accept
< access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
< access-control-allow-origin: *
< age: 0
< cache-control: no-cache
< cache-status: "Netlify Durable"; fwd=bypass
< cache-status: "Netlify Edge"; fwd=miss
< content-type: application/json
< date: Mon, 11 May 2026 11:27:13 GMT
< netlify-vary: query
< server: Netlify
< strict-transport-security: max-age=31536000
< x-nf-request-id: 01KRBCN30H905H5HW4V0ATGK3H
< 
{
  "method": "GET",
  "args": {},
  "data": "",
  "headers": {
    "accept": "*/*,image/webp",
    "cdn-loop": "netlify",
    "host": "echo.hoppscotch.io",
    "netlify-agent-category": "tooling; custom-code",
    "netlify-invocation-source": "client",
    "traceparent": "00-019e16ca8c11480b12c784d815a84c71-98a737e33c491c30-01",
    "user-agent": "curl/8.15.0",
    "x-country": "LU",
    "x-forwarded-for": "158.64.182.90, 3.127.101.13",
    "x-forwarded-proto": "https",
    "x-nf-account-id": "5e2b91527eb7a24fb0054390",
    "x-nf-account-tier": "account_type_free",
    "x-nf-client-connection-ip": "158.64.182.90",
    "x-nf-deploy-context": "production",
    "x-nf-deploy-id": "626b1bc6a7f6c1000902602e",
    "x-nf-deploy-published": "1",
    "x-nf-geo": "eyJjaXR5IjoiU29sZXV2cmUiLCJjb3VudHJ5Ijp7ImNvZGUiOiJMVSIsIm5hbWUiOiJMdXhlbWJvdXJnIn0sInBvc3RhbF9jb2RlIjoiTC00NDE4Iiwic3ViZGl2aXNpb24iOnsiY29kZSI6IkVTIiwibmFtZSI6IkVzY2gtc3VyLUFsemV0dGUifSwidGltZXpvbmUiOiJFdXJvcGUvTHV4ZW1ib3VyZyIsImxhdGl0dWRlIjo0OS41MjYyLCJsb25naXR1ZGUiOjUuOTQ2NX0=",
    "x-nf-request-id": "01KRBCN30H905H5HW4V0ATGK3H",
    "x-nf-request-start": "1778498833623807400",
    "x-nf-site-id": "5d797a9d-fe11-4582-8837-9986a4673158",
    "x-nf-trace-span-id": "ca31e4259f35f26a"
  },
  "path": "/",
  "isBase64Encoded": true
* Connection #0 to host echo.hoppscotch.io left intact
}%

----------------------------------------------------------------------------------------------------------

# What's an endpoint?

an endpoint is a specific point where something starts, ends or can be accessed - especially in tech

for APIs:

an **endpoint** is a **URL** where you can interact with a service.

    https://api.weather.com/v1/current

This is an endpoint that might return current weather data

Think of it like:

- a door to a system
- you send a request → it sends back data

## Real world analogy

Imagine ordering food:

- the restaurant counter is the endpoint
- we go there (request) → place an order → get my food (response)

--------------------------------

# A Query String?

Syntax:

- starts with a **?**
- parameters key=value

    /products?price_min=5?price_max=100
    
--------------------------------

# Response

Response status codes:

- 2xx (success)

- 3xx (redirection)

- 4xx (client error)

- 5xx (server error)
    
# Crud operations?

C → create → POST
R → read → GET
U → update → PUT/PATCH
D → delete → DELETE

* (put → updates a user full, patch → updates a user partial)
