# CRUD

1. In your own words, describe what each group of status code represents:
    **100’s** = They usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.
    **200’s** = They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.
    **300’s** =They tell the client that the resource they are requesting isn’t available at the expected location anymore.
    **400’s** = They are all about invalid requests a client sent to a server.
    **500’s** = Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server.
2. What is a status code 202?
    Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future.
3. What is a status code 308?
    This is the right code if the resource will now be available at a new URL and the client should directly access it via the new URL in the future.
4. What code would you use if an update didn’t return data to a client?
    *204 No Content*
5. What code would you use if a resource used to exist but no longer does?
    **410 Gone**
6. What is the ‘Forbidden’ status code?
    **403 Forbidden** - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.
