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

## `content-type`
available content type includes current valid media type which is ruled by IANA (mentioned in this article -- valid media types[^1])

or see [media type.md(my notes at GitHub)](https://github.com/40843245/Network/blob/main/media/media%20type.md)

## `content-encoding`
### structure
Use RE (regular expression), it can be represented as follows.

```
{content-encoding} := {directive}(,{directive})*
```

where directive is one of followings.

```
{directive} := ({gzip}|{compress}|{deflate}|{br}|{zstd})
```

### directive
[`gzip`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding#gzip)

A format using the [Lempel-Ziv coding](https://en.wikipedia.org/wiki/LZ77_and_LZ78#LZ77) (LZ77), with a 32-bit CRC. This is the original format of the UNIX _gzip_ program. The HTTP/1.1 standard also recommends that the servers supporting this content-encoding should recognize `x-gzip` as an alias, for compatibility purposes.

[`compress`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding#compress)

A format using the [Lempel-Ziv-Welch](https://en.wikipedia.org/wiki/LZW) (LZW) algorithm. The value name was taken from the UNIX _compress_ program, which implemented this algorithm. Like the compress program, which has disappeared from most UNIX distributions, this content-encoding is not used by many browsers today, partly because of a patent issue (it expired in 2003).

[`deflate`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding#deflate)

Using the [zlib](https://en.wikipedia.org/wiki/Zlib) structure (defined in [RFC 1950](https://datatracker.ietf.org/doc/html/rfc1950)) with the [deflate](https://en.wikipedia.org/wiki/Deflate) compression algorithm (defined in [RFC 1951](https://datatracker.ietf.org/doc/html/rfc1951)).

[`br`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding#br)

A format using the [Brotli](https://developer.mozilla.org/en-US/docs/Glossary/Brotli_compression) algorithm structure (defined in [RFC 7932](https://datatracker.ietf.org/doc/html/rfc7932)).

[`zstd`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding#zstd)

A format using the [Zstandard](https://developer.mozilla.org/en-US/docs/Glossary/Zstandard_compression) algorithm structure (defined in [RFC 8878](https://datatracker.ietf.org/doc/html/rfc8878)).

## `host`
### structure

```
{host}: {DNS}:{port}
```

where 

`DNS` stands for `Domain Name Server`

and 

`port` is port number.

## `user-agent`
With RE (regular expression), it can be presented as followings.

```
{user-Agent} := {product} / {product-version} {comment}
```

### examples of `user-agent`

```
user-agent := Mozilla/5.0 (<system-information>) <platform> (<platform-details>) <extensions>
```

Here, it indicates that user-agent is a browser `Mozilla` with version 5.0.

## `accept`
### structure

With RE (regular expression), it can be represented as followings. 

```
{accept} := ({MIME_type}/{MIME_subtype}) | ({MIME_type}/{any}) | ({any}/{any})
```

where 

```
{any} := "*"
```

that indicates it can accept any type.

and 

{MIME_type}, {MIME_subtype} is mentioned as above `content-type` section.

## source
The above figure is from screenshot of `POSTMAN`. 

## reference
About explanation of `host`, see [`Host`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host)

About explanation of `accept`, see [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept)

About explanation of `content-encoding`, [`content-encoding`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding)

## see also
To learn more about `current valid media type`, see [meida type.md (my notes at GitHub)](https://github.com/40843245/Network/blob/main/media/media%20type.md) or see this article -- valid media types[^1]

## further reading
About detailed explanation of `user-agent` and `product`, see [HTTP Headers – User-Agent](https://www.geeksforgeeks.org/http-headers-user-agent/)

About all `content-type` in request header, see [`content-type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type)

[^1]: [valid media types (last update in 2024/11/05)](https://www.iana.org/assignments/media-types/media-types.xhtml)
