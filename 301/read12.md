>> In your own words, describe what each group of status code represents:

100’s = This interim response indicates that everything so far is OK and that the client should continue the request, or ignore the response if the request is already finished.
200’s = The request has succeeded. The meaning of the success depends on the HTTP method
300’s = The request has more than one possible response.
400’s = The server could not understand the request due to invalid syntax.
500’s = The server has encountered a situation it doesn't know how to handle.

>> What is a status code 202?

### The HyperText Transfer Protocol (HTTP) 202 Accepted response status code indicates that the request has been accepted for processing, but the processing has not been completed

>> What is a status code 308?

### The HyperText Transfer Protocol (HTTP) 308 Permanent Redirect redirect status response code indicates that the resource requested has been definitively moved to the URL given by the Location headers

>> What code would you use if an update didn’t return data to a client?

### 204/  404

>> What is the ‘Forbidden’ status code?

### The HTTP 403 Forbidden client error status response code indicates that the server understood the request but refuses to authorize it. This status is similar to 401 , but in this case, re-authenticating will make no difference

>> Why do we need to pull our MongoDB database string out of our server and put it into our .env?

### Becuase its using a local host string path and when we deploy our application it won’t be in our local host so we put it in .env.

>>  What is middleware?

### Middleware is software that provides common services and capabilities to applications outside of what’s offered by the operating system.

>>  What does the /:id mean in a route?

### The route will be the passed id argument in the middleware function.

>> What is the difference beween PUT and PATCH?

### PUT is used to update an existing resource. PATCH is used to update a portion of an existing resource.

>> What does a 500 error status code mean?

### Internal Server Error

>> What is the difference between a status 200 and a status 201?

### 200: OK, it’s the basic status code to tell the client everything went good. 201: Created, the most fitting for Create operations. This code should signal backend-side resource creation and come along with a Location header that defines the most specific URL for that newly created resource.


