# HTTP headers
## structure
It must contain at least 7 key-value pairs. Shown as follows.

<img width="584" alt="image" src="https://github.com/user-attachments/assets/fbb59fce-5b48-43c2-bae8-909948df217e">

1. `content-type`: determine the type of content in request (i.e. body in request) when the request is sent.
2. `content-length`: the length of content in request (i.e. body in request) when the request is sent.
3. `host`: specifies the host and port number of the server to which the request is being sent.
4. `user-agent`: records the info of product.
5. `accept`: indicates the client can accept the request (i.e. is able to recognize and understand the request).
6. `accept-encoding`: indicates how the client recognizes and understands the request (issues like what the encoding of the request).
7. `connection`: indicats the state of connection. (For example, when the connection is connected successfully and has not been closed yet, the connection is `keep-alive`.)

## content type
available content type includes current valid media type which is ruled by IANA (mentioned in this article -- valid media types[^1])

## source
The above figure is from screenshot of `POSTMAN`. 

## reference
About explanation of `host`, see [`Host`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host)

About explanation of `host`, see [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept)

## further reading
About detailed explanation of `user-agent` and `product`, see [HTTP Headers – User-Agent](https://www.geeksforgeeks.org/http-headers-user-agent/)

About all `content-type` in request header, see [`content-type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type)

[^1]: [valid media types (last update in 2024/11/05)](https://www.iana.org/assignments/media-types/media-types.xhtml)
