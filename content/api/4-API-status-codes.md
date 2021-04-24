---
title: "3. API status codes"
metaTitle: "API status codes for testers"
metaDescription: "Learn API status codes Codemify"
---

### API Status Codes(Response Codes)

You don't have to memorize every each of them, but it would be nice to know the most common once that we will mark in red.

**DESCRIPTION**

**1xx: Informational** - Communicates transfer protocol-level information.

**2xx: Success** - Client’s request was accepted successfully.

**3xx: Redirection** - Client must take some additional action in order to complete their request.

**4xx: Client Error** - This category of error status codes points the finger at clients.

**5xx: Server Error** - The server takes responsibility for these error status codes.

---

### 200 (OK)

It means that REST API has successfully returned response for whatever action the client requested.

Unlike the 204 status code, a 200 response includes a response body.The information returned with the response dependents on the method used in the request.

### 201 (Created)

Success status response code 201 indicates that resource was created. It will be used as a response to POST request of creating a new resource.

### 202 (Accepted)

A 202 success response is typically used for actions that take a long while to process. It indicates that request has been accepted for processing, but the processing has not been completed.

### 204 (No Content)

The 204 success status code is usually returned in response to a PUT, POST, or DELETE request, when the REST API does not send any response message in a response body.

The 204 response will NOT include a message-body.


### 301 (Moved Permanently)

Redirect status code indicates that the resource requested has been moved to the URL given by the Location headers.

You will hardly see this response code.


### 302 (Found)

The HTTP status code 302 Found is a way of performing URL redirection. This response with this status code will additionally provide a URL in the location header field.


### 303 (See Other)

The response to the request can be found in another URI using the GET method. When received in response to a POST (or PUT/DELETE), the client should assume that the server has received the data and should send a new GET request to the given URI.


### 304 (Not Modified)

This status code is similar to 204 (“No Content”) in that the response body must be empty. The key difference is that 204 is used when there is nothing to send in the body, but 304 is used when the resource has not been modified since the version specified by the request headers If-Modified-Since or If-None-Match.


### 400 (Bad Request)

400 is the generic client-side error status code, used when no other 4xx error code is appropriate. Errors like malformed request syntax, invalid request message parameters, or deceptive request routing etc will get this response code.

### 401 (Unauthorized)

Similar to 403 Forbidden, but specifically for use when authentication is required and has failed or has not yet been provided. Example could be you sending request to the server that requires token in a header, but you didn't add it.


### 403 (Forbidden)

A 403 error response indicates that request was valid, but server is declining to send a response. User might not have the necessary permissions for a resource.


### 404 (Not Found)

The requested resource could not be found.  

You all have seen while searching in the browser for something that does not exist.


### 405 (Method Not Allowed)

Request method is not supported.
As an example example: You send GET request instead of POST that requires data, or a PUT request on a read-only resource.

### 406 (Not Acceptable)

The 406 error response indicates that the API is not acceptable according to the Accept headers sent in the request.

### 500 (Internal Server Error)

500 is the generic REST API error response that indicates that unexpected condition was encountered.


### 501 (Not Implemented)

The server either does not recognize the request method, or it lacks the ability to fulfill the request. Usually this means that i will be availability in a future.
