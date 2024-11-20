# MIME type
current valid media type[^1] defined in IANA can be categorized into several main parts:

- [application](https://www.iana.org/assignments/media-types/media-types.xhtml#application)
- [audio](https://www.iana.org/assignments/media-types/media-types.xhtml#audio)
- [example](https://www.iana.org/assignments/media-types/media-types.xhtml#example)
- [font](https://www.iana.org/assignments/media-types/media-types.xhtml#font)
- [haptics](https://www.iana.org/assignments/media-types/media-types.xhtml#haptics)
- [image](https://www.iana.org/assignments/media-types/media-types.xhtml#image)
- [message](https://www.iana.org/assignments/media-types/media-types.xhtml#message)
- [model](https://www.iana.org/assignments/media-types/media-types.xhtml#model)
- [multipart](https://www.iana.org/assignments/media-types/media-types.xhtml#multipart)
- [text](https://www.iana.org/assignments/media-types/media-types.xhtml#text)
- [video](https://www.iana.org/assignments/media-types/media-types.xhtml#video)

## structure 
With RE (regular expression), MIME can be represented as

```
{MIME} := {MIME_type} "/" {tree} ("." {MIME_subtype})? ("+" {suffix})? (";" {parameter})? ;
```

where {MIME_type} can be one of followings.

```
{MIME_type} := ({application}|{audio}|{image}|{model}|{multipart}|{text})

{application} := "application"
{audio} := "audio"
{image} := "image"
{model} := "model"
{multipart} := "multipart"
{text} := "text"
```

As an example, an HTML file might be designated `text/html; charset=UTF-8`. Here, `text` is the type, `html` is the subtype, and `charset=UTF-8` is an optional parameter indicating the character encoding. 

See media type (Wiki)[^2] 

### Common examples of ({MIME_type} "/" {tree})

\[[edit](https://en.wikipedia.org/w/index.php?title=Media_type&action=edit&section=10 "Edit section: Common examples")\]

From the IANA registry:<sup id="cite_ref-iana_1-4" class="reference"><a href="https://en.wikipedia.org/wiki/Media_type#cite_note-iana-1"><span class="cite-bracket">[</span>1<span class="cite-bracket">]</span></a></sup>

- `application/json`
- `application/ld+json` ([JSON-LD](https://en.wikipedia.org/wiki/JSON-LD "JSON-LD"))
- `application/msword` (.doc)
- `application/pdf`
- `application/sql`
- `application/vnd.api+json`
- `application/vnd.microsoft.portable-executable` (.efi, .exe, .dll)
- `application/vnd.ms-excel` (.xls)
- `application/vnd.ms-powerpoint` (.ppt)
- `application/vnd.oasis.opendocument.text` (.odt)
- `application/vnd.openxmlformats-officedocument.presentationml.presentation` (.pptx)
- `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet` (.xlsx)
- `application/vnd.openxmlformats-officedocument.wordprocessingml.document` (.docx)
- `application/x-www-form-urlencoded`
- `application/xml`
- `application/zip`
- `application/zstd` (.zst)
- `audio/mpeg`
- `audio/ogg`
- `image/avif`
- `image/jpeg` (.jpg, .jpeg, .jfif, .pjpeg, .pjp) <sup id="cite_ref-19" class="reference"><a href="https://en.wikipedia.org/wiki/Media_type#cite_note-19"><span class="cite-bracket">[</span>19<span class="cite-bracket">]</span></a></sup>
- `image/png`
- `image/svg+xml` (.svg)
- `image/tiff` (.tif)
- `model/obj` (.obj)
- `multipart/form-data`
- `text/plain`
- `text/css`
- `text/csv`
- `text/html`
- `text/javascript`(.js)
- `text/xml`

### details of common pattern
+ `multipart/form-data` indicates that a request can contain a Body that has more different type of data for sending. 

For example, in gmail, to send an json string and an image. One has to set the content type as `multipart/form-data`. 

### notice of common pattern
+ `application/json` indicates that a request can contain a Body with a json string.

notice that, although a json string a kind of text. DON'T use `text/json`.

+ `application/sql` indicates that a request can contain a Body with a sql command.
  
notice that, although a sql command can be represented as text. DON'T use `text/sql`.

### difference of between pattern
> [!NOTE]
> [What is the difference between `application/xml` and `text/xml`?](https://stackoverflow.com/questions/4832357/whats-the-difference-between-text-xml-vs-application-xml-for-webservice-respons)

### (extra bonus) question about `content-type`

Thank's to all who ask this question and answer this question [application/x-www-form-urlencoded or multipart/form-data? provides lots of details about content-type in request.]
(https://stackoverflow.com/questions/4007969/application-x-www-form-urlencoded-or-multipart-form-data). 

It provides lots of details about `content-type`.

1. max asks a question When to use `application/x-www-form-urlencoded` and `multipart/form-data`?

According to Matt Bridges's answer,

Summary, if you have binary (non-alphanumeric) data (or a significantly sized payload) to transmit, use `multipart/form-data`. Otherwise, use `application/x-www-form-urlencoded`.

<img width="546" alt="image" src="https://github.com/user-attachments/assets/2e31e215-df41-446d-a493-4160e79e0767">

According to EML's answer,

**READ AT LEAST THE FIRST PARA HERE!**

I know this is 3 years too late, but Matt's (accepted) answer is incomplete and will eventually get you into trouble. The key here is that, if you choose to use `multipart/form-data`, the boundary must _not_ appear in the file data that the server eventually receives.

This is not a problem for `application/x-www-form-urlencoded`, because there is no boundary. `x-www-form-urlencoded` can also always handle binary data, by the simple expedient of turning one arbitrary byte into three `7BIT` bytes. Inefficient, but it works (and note that the comment about not being able to send filenames as well as binary data is incorrect; you just send it as another key/value pair).

The problem with `multipart/form-data` is that the boundary separator must not be present in the file data (see [RFC 2388](https://www.rfc-editor.org/rfc/rfc2388#section-5.2); section 5.2 also includes a rather lame excuse for not having a proper aggregate MIME type that avoids this problem).

So, at first sight, `multipart/form-data` is of no value whatsoever in _any_ file upload, binary or otherwise. If you don't choose your boundary correctly, then you _will_ eventually have a problem, whether you're sending plain text or raw binary - the server will find a boundary in the wrong place, and your file will be truncated, or the POST will fail.

The key is to choose an encoding and a boundary such that your selected boundary characters cannot appear in the encoded output. One simple solution is to use `base64` (do _not_ use raw binary). In [base64](http://en.wikipedia.org/wiki/Base64) 3 arbitrary bytes are encoded into four 7-bit characters, where the output character set is `[A-Za-z0-9+/=]` (i.e. alphanumerics, '+', '/' or '='). `=` is a special case, and may only appear at the end of the encoded output, as a single `=` or a double `==`. Now, choose your boundary as a 7-bit ASCII string which cannot appear in `base64` output. Many choices you see on the net fail this test - the MDN forms [docs](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Sending_forms_through_JavaScript), for example, use "blob" as a boundary when sending binary data - not good. However, something like "!blob!" will never appear in `base64` output.

<img width="548" alt="image" src="https://github.com/user-attachments/assets/8a4660a8-993f-4949-88de-6068cfbc7c7d">

<img width="509" alt="image" src="https://github.com/user-attachments/assets/862a92ff-db9c-4abe-9572-c0ac9dfd486e">

> P.S.
>
> That's the reason why it uses `base64` to handle the body of a request in ron's project demo.

Example of sending an image and other data (from manuel aldana's answer)

```
POST /images
Content-type: multipart/mixed; boundary="xxxx" 
... multipart data

201 Created
Location: http://imageserver.org/../foo.jpg
```


2. Pacerier asks a question Does `application/x-www-form-urlencoded` have a length limit, or is it unlimited?

<img width="482" alt="image" src="https://github.com/user-attachments/assets/cba30537-c236-4183-ba22-855a3b6db20a">

According to Matt Bridges's answer,

The limit is enforced by the server receiving the POST request. 

### common pattern of (; {parameter})?

As an example, an HTML file might be designated `text/html; charset=UTF-8`. Here, `text` is the type, `html` is the subtype, and `charset=UTF-8` is an optional parameter indicating the character encoding. 

## see also
[content type of HTTP header (my notes at GitHub)](https://github.com/40843245/Network/blob/main/Network%20Protocol/category/HTTP/HTTP%20headers.md#content-type)

[^1]: [valid media types (last update in 2024/11/05)](https://www.iana.org/assignments/media-types/media-types.xhtml)

[^2] [media type (Wiki)](https://en.wikipedia.org/wiki/Media_type)
