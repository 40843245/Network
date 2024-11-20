# HTTP headers
## structure
It must contain at least 8 key-value pairs. Shown as follows.

<img width="584" alt="image" src="https://github.com/user-attachments/assets/fbb59fce-5b48-43c2-bae8-909948df217e">

1. `content-type`: determine the type of content in request (i.e. body in request) when the request is sent.
2. `content-length`: the length of content in request (i.e. body in request) when the request is sent.
3. `host`: specifies the host and port number of the server to which the request is being sent.
4. `user-agent`: records the info of product. 

## source
The figure is screenshot of `POSTMAN`. 

## reference
About explanation of `host`, see [`Host`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host)

## further reading
About detailed explanation of `user-agent` and `product`, see [HTTP Headers – User-Agent](https://www.geeksforgeeks.org/http-headers-user-agent/)
