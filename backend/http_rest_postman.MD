## Web Applications
1. frontend: front of house
2. backend: kichen

# HTTP
- computers use HTTP to talk to other computers
- the edge connecting computer (nodes) in a graph

## HTTP Request
1. Header
2. Body

Example:
'''
GET /home.html HTTP/1.1
Host: developer.mozilla.org
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: https://developer.mozilla.org/testpage.html
Connection: keep-alive
Upgrade-Insecure-Requests: 1
If-Modified-Since: Mon, 18 Jul 2016 02:36:04 GMT
If-None-Match: "c561c68d0ba92bbeb8b0fff2a9199f722e3a621a"
Cache-Control: max-age=0
'''

## Methods
1. GET: The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
2. HEAD: The HEAD method asks for a response identical to that of a GET request, but without the response body.
3. POST: The POST method is used to submit an entity (a form) to the specified resource, often causing a change in state or side effects on the server.
4. PUT: The PUT method replaces all current representations of the target resource with the request payload. In other words, you can use PUT to update a resource.
5. DELETE: TheDELETE method deletes the specified resource.
6. CONNECT: TheCONNECT method establishes a tunnel to the server identified by the target resource.
7. OPTIONS: The OPTIONS method is used to describe the communication options for the target resource.
8. TRACE: The TRACE method performs a message loop-back test along the path to the target resource.
9. PATCH: The PATCH method is used to apply partial modifications to a resource.

## HTTP Responses
- The server always sends a response indicating that it received a request
- Response header:
  - 1XX: Informational
  - 2XX: Successful
  - 3XX: Redirection
  - 4XX: Client Error
  - 5XX: Server Error
- Response codes:
  - 200: OK. Meaning that the request of a specific resource (list of TODOs) are successful.
  - 201: Created. Meaning that a resource is created / updated successfully.
  - 401: Unauthorized. Meaning that the request is unauthorized, the client needs to be logged in.
  - 403: Forbidden. Meaning that the resource is not available for the client.
  - 404: Not found. Meaning that the resource accessing is not served.
  - 418: I'm a teapot. Meaning that the server refuses the attempt to brew coffee with a teapot.
  - 500: Server error.

### curl vs. browser
- curl is your machine's built in way of making requests to external websites.

'curl https://pokeapi.co/api/v2/pokemon/ditto'

- Entering a URL into your browser is the same as making a GET request

### Request Anatomy
- 'https://' defines the protocol
- '[pokeapi.co/](http://pokeapi.com/)' defines the server to which we are making our request
- '/api/v2/pokemon/ditto' where we are making our request

## REST API
1. Client-server – By separating the user interface concerns from the data storage concerns, we improve the portability of the user interface across multiple platforms and improve scalability by simplifying the server components.
2. Stateless – Each request from client to server must contain all of the information necessary to understand the request, and cannot take advantage of any stored context on the server. Session state is therefore kept entirely on the client.
3. Cacheable – Cache constraints require that the data within a response to a request be implicitly or explicitly labeled as cacheable or non-cacheable. If a response is cacheable, then a client cache is given the right to reuse that response data for later, equivalent requests.
4. Uniform interface – By applying the software engineering principle of generality to the component interface, the overall system architecture is simplified and the visibility of interactions is improved. In order to obtain a uniform interface, multiple architectural constraints are needed to guide the behavior of components. REST is defined by four interface constraints: identification of resources; manipulation of resources through representations; self-descriptive messages; and, hypermedia as the engine of application state.
5. Layered system – The layered system style allows an architecture to be composed of hierarchical layers by constraining component behavior such that each component cannot “see” beyond the immediate layer with which they are interacting.
6. Code on demand (optional) – REST allows client functionality to be extended by downloading and executing code in the form of applets or scripts. This simplifies clients by reducing the number of features required to be pre-implemented.

## Postman
