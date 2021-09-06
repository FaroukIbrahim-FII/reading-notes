# APIs

1. REST is an architectural style for building distributed systems based on hypermedia,REST is independent of any underlying protocol and is not necessarily tied to HTTP

2. resources

3. [https://adventure-works.com/orders/1](https://adventure-works.com/orders/1)

4. The most common HTTP verbs are:
   * GET retrieves a representation of the resource at the specified URI. The body of the response message contains the details of the requested resource.
   * POST creates a new resource at the specified URI. The body of the request message provides the details of the new resource. Note that POST can also be used to trigger operations that don't actually create resources.
   * PUT either creates or replaces the resource at the specified URI. The body of the request message specifies the resource to be created or updated.
   * PATCH performs a partial update of a resource. The request body specifies the set of changes to apply to the resource.
   * DELETE removes the resource at the specified URI.

5. On the resource and not verbs.

6. [https://www.adventure-works.com/](https://www.adventure-works.com/)

7. try to avoid "chatty" web APIs that expose a large number of small resources.

8. A successful GET method typically returns HTTP status code 200 (OK)

9. The method should return 404 (Not Found).

10. Returns HTTP status code 200 and include the result of the operation in the response body.

11. Respond with HTTP status code 204, indicating that the process has been successfully handled.
