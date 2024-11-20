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
By regular expression, MIME can be represented as

```
mime-type = type "/" [tree "."] subtype ["+" suffix]* [";" parameter];
```

As an example, an HTML file might be designated `text/html; charset=UTF-8`. In this example, `text` is the type, `html` is the subtype, and `charset=UTF-8` is an optional parameter indicating the character encoding. 

See media type (Wiki)[^2] 

## common examples

### Common examples

\[[edit](https://en.wikipedia.org/w/index.php?title=Media_type&action=edit&section=10 "Edit section: Common examples")\]

From the IANA registry:<sup id="cite_ref-iana_1-4" class="reference"><a href="https://en.wikipedia.org/wiki/Media_type#cite_note-iana-1"><span class="cite-bracket">[</span>1<span class="cite-bracket">]</span></a></sup>

.mw-parser-output .div-col{margin-top:0.3em;column-width:30em}.mw-parser-output .div-col-small{font-size:90%}.mw-parser-output .div-col-rules{column-rule:1px solid #aaa}.mw-parser-output .div-col dl,.mw-parser-output .div-col ol,.mw-parser-output .div-col ul{margin-top:0}.mw-parser-output .div-col li,.mw-parser-output .div-col dd{page-break-inside:avoid;break-inside:avoid-column}

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

## see also
[content type of HTTP header (my notes at GitHub)](https://github.com/40843245/Network/blob/main/Network%20Protocol/category/HTTP/HTTP%20headers.md#content-type)

[^1]: [valid media types (last update in 2024/11/05)](https://www.iana.org/assignments/media-types/media-types.xhtml)

[^2] [media type (Wiki)](https://en.wikipedia.org/wiki/Media_type)
