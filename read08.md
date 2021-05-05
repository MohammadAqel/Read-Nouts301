What is REST?
 (Links to an external site.)In 2000, Roy Fielding proposed Representational State Transfer (REST) as an architectural approach to designing web services. REST is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP. However, most common REST implementations use HTTP as the application protocol, and this guide focuses on designing REST APIs for HTTP.
 (Links to an external site.)REST, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other. REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server. We will go into what these terms mean and why they are beneficial characteristics for services on the Web.
 (Links to an external site.)REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client. REST API n is designed to take advantage of existing protocols. While REST can be used over nearly any protocol, it usually takes advantage of HTTP when used for Web APIs. This means that developers do not need to install libraries or additional software in order to take advantage of a REST API design.

 A resource doesn't have to be based on a single physical data item. For example, an order resource might be implemented internally as several tables in a relational database, but presented to the client as a single entity. Avoid creating APIs that simply mirror the internal structure of a database. The purpose of REST is to model entities and the operations that an application can perform on those entities. A client should not be exposed to the internal implementation.
 (Links to an external site.)Entities are often grouped together into collections (orders, customers). A collection is a separate resource from the item within the collection, and should have its own URI. For example, the following URI might represent the collection of orders:
image

 (Links to an external site.)Sending an HTTP GET request to the collection URI retrieves a list of items in the collection. Each item in the collection also has its own unique URI. An HTTP GET request to the item's URI returns the details of that item.
 (Links to an external site.)What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
 (Links to an external site.)Chatty API is one that requires consumer to make tremendous (subjective matter) amount of distinct API calls to get needed information about a resource. George Reese has defined chatty API as any API that requires consumer to do more than a single call to perform a single, common operation.
 (Links to an external site.)The more requests, the bigger the load. Therefore, try to avoid "chatty" web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires. Instead, you might want to denormalize the data and combine related information into bigger resources that can be retrieved with a single request. However, you need to balance this approach against the overhead of fetching data that the client doesn't need. Retrieving large objects can increase the latency of a request and incur additional bandwidth costs.

 URL (Uniform Resource Identifier) : sequence of characters that identifies resource . based standards on resource(nouns ) and the operation of the resource (not verbs).

example of Good URL : https://adventure-works.com/orders

‘Chatty’ web API : if designed the wrong resources for clients . and it is bad thing to make large number of small resources.

Successful Get request return : HTTP code 200 (ok).

Unsuccessful Get request return : HTTP code 400 (not found).

Successful POST request return : HTTP code 201 (created). code 204 (no content).

Successful DELETE request return : HTTP code 204 (accepted) . code 404 (not found).

HATEOAS
URI - Uniform Resource Identifier.

HATEOAS - Hypermedia as the Engine of Application State - clients interact with a certain network app whose app servers return information through hypermedia. Contains only the info necessary to shift to one atate from another.

MIME - Multipurpose Internet Mail Extensions - extends format of emails messages and supports attachments like audio/video.

URI versioning - Adding a version number to the URI for each of the resources. This will allow other versions to continue to operate. This, however, may complicate HATEOAS.

Query string versioning - add a version number of the desired resource using a parameter contained in your query string which will be appended to the HTTP request. Has some of the same complications with HATEOAS.

Header versioning - use a custom header that indicates the desired version.

Media type versioning - name the desired format using Accept in the header in the request.