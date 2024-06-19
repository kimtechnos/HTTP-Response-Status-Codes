# HTTP Response Status Codes

HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are categorized into several classes:

1. [Informational responses (100 - 199)](#informational-responses)
2. [Successful responses (200 - 299)](#successful-responses)
3. [Redirection messages (300 - 399)](#redirection-messages)
4. [Client error responses (400 - 499)](#client-error-responses)
5. [Server error responses (500 - 599)](#server-error-responses)

## Informational Responses

### 100 Continue

- **Meaning:** The initial part of the request was received, and the client should proceed with the rest of the request or ignore the response.
- **Usage:** Allows the server to inform the client to continue with the request.

### 101 Switching Protocols

- **Meaning:** The server is switching protocols as requested by the client's `Upgrade` header.
- **Usage:** Typically used when upgrading from HTTP to a different protocol like WebSocket.

### 102 Processing (WebDAV)

- **Meaning:** The server has received the request and is processing it, but no response is available yet.
- **Usage:** Prevents client timeouts during long processing times.

### 103 Early Hints

- **Meaning:** Provides early information to the client about resources that will be needed for the requested page.
- **Usage:** Allows preloading or preconnecting resources while the server prepares a response.

## Successful Responses

### 200 OK

- **Meaning:** The request was successful.
- **Usage:** Various HTTP methods (GET, POST, PUT, etc.) can result in a 200 response indicating success.

### 201 Created

- **Meaning:** The request has been fulfilled, resulting in the creation of a new resource.
- **Usage:** Typically follows a POST request that creates a new resource.

### 202 Accepted

- **Meaning:** The request has been accepted for processing, but the processing has not been completed.
- **Usage:** Used when the outcome is uncertain or handled by another process.

### 203 Non-Authoritative Information

- **Meaning:** The returned metadata is from a local or third-party copy, not the original server.
- **Usage:** Commonly used in caching scenarios where a mirror or backup server responds.

### 204 No Content

- **Meaning:** The request was successful, but there is no content to return.
- **Usage:** Often used in update operations where no response body is needed.

### 205 Reset Content

- **Meaning:** The request was successful, and the client should reset the document view.
- **Usage:** Instructs the client to clear the form used for submitting data.

### 206 Partial Content

- **Meaning:** The server is delivering only part of the resource due to a range header sent by the client.
- **Usage:** Used when the client requests only a portion of a resource.

### 207 Multi-Status (WebDAV)

- **Meaning:** Provides status for multiple independent operations on different resources.
- **Usage:** Commonly used in WebDAV operations.

### 208 Already Reported (WebDAV)

- **Meaning:** The members of a DAV binding have already been enumerated in a previous reply to the same request.
- **Usage:** Avoids repeating the same resource listing in WebDAV responses.

### 226 IM Used (HTTP Delta encoding)

- **Meaning:** The server has fulfilled a GET request for the resource, applying one or more instance manipulations.
- **Usage:** Used in HTTP Delta encoding scenarios.

## Redirection Messages

### 300 Multiple Choices

- **Meaning:** Indicates multiple options for the resource that the client may follow.
- **Usage:** Allows user or user agent choice.

### 301 Moved Permanently

- **Meaning:** The requested resource has been permanently moved to a new URL.
- **Usage:** Redirects future requests to the new URL.

### 302 Found

- **Meaning:** The requested resource temporarily resides under a different URL.
- **Usage:** Commonly used for temporary redirects.

### 303 See Other

- **Meaning:** The response to the request can be found at another URL using a GET method.
- **Usage:** Instructs the client to retrieve the response from another location.

### 304 Not Modified

- **Meaning:** Indicates that the resource has not been modified since the version specified by the request headers.
- **Usage:** Used to reduce network traffic by indicating cached resources are valid.

### 305 Use Proxy

- **Meaning:** This status code is no longer used due to security concerns.
- **Usage:** Deprecated and should not be used.

### 307 Temporary Redirect

- **Meaning:** The requested resource resides temporarily under a different URL.
- **Usage:** Requests are redirected with the same method.

### 308 Permanent Redirect

- **Meaning:** The requested resource has been permanently moved to a different URL.
- **Usage:** Similar to 301 but maintains the request method.

## Client Error Responses

**400 Bad Request**
- **Meaning:** The server can't process the request due to an error (e.g., bad request syntax).

**401 Unauthorized**
- **Meaning:** The client needs to authenticate to get the requested response.

**402 Payment Required (Experimental)**
- **Meaning:** Reserved for future use, intended for digital payment systems (rarely used).

**403 Forbidden**
- **Meaning:** The client is authenticated but doesn't have permission to access the resource.

**404 Not Found**
- **Meaning:** The server can't find the requested resource.

**405 Method Not Allowed**
- **Meaning:** The server knows the request method, but it’s not allowed for the target resource.

**406 Not Acceptable**
- **Meaning:** The server can't find content matching the criteria given by the client.

**407 Proxy Authentication Required**
- **Meaning:** Similar to 401, but authentication is required by a proxy.

**408 Request Timeout**
- **Meaning:** The server timed out waiting for the request.

**409 Conflict**
- **Meaning:** The request conflicts with the current state of the server.

**410 Gone**
- **Meaning:** The resource has been permanently deleted from the server.

**411 Length Required**
- **Meaning:** The server needs a Content-Length header in the request.

**412 Precondition Failed**
- **Meaning:** The server doesn't meet the conditions specified in the request headers.

**413 Payload Too Large**
- **Meaning:** The request is too large for the server to process.

**414 URI Too Long**
- **Meaning:** The requested URI is too long for the server to process.

**415 Unsupported Media Type**
- **Meaning:** The server doesn't support the media format of the requested data.

**416 Range Not Satisfiable**
- **Meaning:** The requested range can't be provided by the server.

**417 Expectation Failed**
- **Meaning:** The server can't meet the requirements of the Expect header.

**418 I'm a teapot**
- **Meaning:** The server refuses to brew coffee with a teapot.

**421 Misdirected Request**
- **Meaning:** The request was sent to the wrong server.

**422 Unprocessable Content (WebDAV)**
- **Meaning:** The request is well-formed but can't be processed due to semantic errors.

**423 Locked (WebDAV)**
- **Meaning:** The resource is locked and can't be accessed.

**424 Failed Dependency (WebDAV)**
- **Meaning:** The request failed because a previous request failed.

**425 Too Early (Experimental)**
- **Meaning:** The server is unwilling to process the request because it might be replayed.

**426 Upgrade Required**
- **Meaning:** The server wants the client to switch to a different protocol.

**428 Precondition Required**
- **Meaning:** The server requires the request to be conditional to avoid conflicts.

**429 Too Many Requests**
- **Meaning:** The client has sent too many requests in a given time period.

**431 Request Header Fields Too Large**
- **Meaning:** The server can't process the request because the headers are too large.

**451 Unavailable For Legal Reasons**
- **Meaning:** The requested resource is unavailable due to legal reasons (e.g., censorship).

## Server Error Responses

**500 Internal Server Error**
- **Meaning:** The server encountered an unexpected condition that prevented it from fulfilling the request.

**501 Not Implemented**
- **Meaning:** The server doesn't support the request method.

**502 Bad Gateway**
- **Meaning:** The server, while acting as a gateway or proxy, received an invalid response from an inbound server.

**503 Service Unavailable**
- **Meaning:** The server is not ready to handle the request, often due to maintenance or overload.

**504 Gateway Timeout**
- **Meaning:** The server, while acting as a gateway or proxy, didn't receive a timely response from an upstream server.

**505 HTTP Version Not Supported**
- **Meaning:** The server doesn't support the HTTP protocol version used in the request.

**506 Variant Also Negotiates**
- **Meaning:** The server has a configuration error with transparent content negotiation.

**507 Insufficient Storage (WebDAV)**
- **Meaning:** The server cannot store the data needed to complete the request.

**508 Loop Detected (WebDAV)**
- **Meaning:** The server detected an infinite loop while processing the request.

**510 Not Extended**
- **Meaning:** The server requires further extensions to fulfill the request.

**511 Network Authentication Required**
- **Meaning:** The client needs to authenticate to gain network access.



# HTTP-Response-Status-Codes
