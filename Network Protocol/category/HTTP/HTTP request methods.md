# HTTP request methods
## category
[`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET)

The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data and should not contain a request [content](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_Content).

[`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD)

The `HEAD` method asks for a response identical to a `GET` request, but without a response body.

[`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)

The `POST` method submits an entity to the specified resource, often causing a change in state or side effects on the server.

[`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT)

The `PUT` method replaces all current representations of the target resource with the request [content](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_Content).

[`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE)

The `DELETE` method deletes the specified resource.

[`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT)

The `CONNECT` method establishes a tunnel to the server identified by the target resource.

[`OPTIONS`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS)

The `OPTIONS` method describes the communication options for the target resource.

[`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE)

The `TRACE` method performs a message loop-back test along the path to the target resource.

[`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH)

The `PATCH` method applies partial modifications to a resource.

## comparison table

| Method | Safe | Idempotent | Cacheable |
| --- | --- | --- | --- |
| [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) | Yes | Yes | Yes |
| [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) | Yes | Yes | Yes |
| [`OPTIONS`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS) | Yes | Yes | No |
| [`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE) | Yes | Yes | No |
| [`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) | No | Yes | No |
| [`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) | No | Yes | No |
| [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) | No | No | Conditional\* |
| [`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) | No | No | Conditional\* |
| [`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT) | No | No | No |

\* `POST` and `PATCH` are cacheable when responses explicitly include [freshness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching) information and a matching [`Content-Location`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Location) header.
