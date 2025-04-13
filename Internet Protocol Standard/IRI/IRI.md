# IRI (Internationalized Resource Identifier)
## pros
Mostly, it makes it easier for users who are unfamiliar with the Latin (A–Z) alphabet. 

Assuming that it isn't too difficult for anyone to replicate arbitrary Unicode on their keyboards, 

this can make the URI system more accessible

## cons
Mixing IRIs and ASCII URIs can make it much easier to execute phishing attacks that trick someone into believing they are on a different site than they really are.

For example, 

one can replace an ASCII "a" in `www.myfictionalbank.com` with the Unicode look-alike "[α](https://en.wikipedia.org/wiki/%CE%91 "Α")" to give `www.myfictionαlbank.com` and 

point that IRI to a malicious site. 

This is known as an [IDN homograph attack](https://en.wikipedia.org/wiki/IDN_homograph_attack "IDN homograph attack").
