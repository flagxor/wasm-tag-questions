# Wasm Response API Tag Questionnaire

## Overview

The WebAssembly Core specification defines a virtual machine which can only interact with the outside world via *host bindings". The JS API host binding specifies how WebAssembly is used in a browser by passing all data and API calls through Javascript in the host environment. Because of this:
… WebAssembly's security and privacy environment is strictly more restrive than that of a worker.
… All interesting built-in capabilities are exposed by operators for computation and resource allocation, i.e. worst case is DOS by resource exhaustion.

## Answers to questions
[here](https://www.w3.org/TR/security-privacy-questionnaire/).

* 3.1 - Does this specification deal with personally-identifiable information?
  * No personally-identifiable information is handled by this API.

* 3.2 - Does this specification deal with high-value data?
  * No high-value data is handled by this API.

* 3.3 - Does this specification introduce new state for an origin that persists
across browsing sessions?
  * Only to the extent that WebAssembly code may, like any other web resource, be stored in caches and proxies.

* 3.4 - Does this specification expose persistent, cross-origin state to the web?
  * In the JS-API, access to WebAssembly resources is via the `fetch()` API. Thus, the only differential access to resources between WebAssembly and conventional Javascript occurs if `fetch("…")` and `<script src="...">` have differnt security policies.

* 3.5 - Does this specification expose any other data to an origin that it
doesn’t currently have access to?
  * On its own, WASM can't be used to  e.g. set up a web server to expose data to which it has access.
  * Withing the JS-API host binding, it is subject to the same cross-origin restrictions as any other Javascript program.

* 3.6 - Does this specification enable new script execution/loading mechanisms?
  * Yes, this API allows origin bound compilation of WebAssembly could from
    Response objects or Promises of Response objects.

* 3.7 - Does this specification allow an origin access to a user’s location?
  * No, this API does not involve location info.

* 3.8 - Does this specification allow an origin access to sensors on a user’s
        device?
  * No, this API does not involve sensor info.

* 3.9 - Does this specification allow an origin access to aspects of a user’s
        local computing environment?
  * No, this API does not involve access to the local computing environment.

* 3.10 - Does this specification allow an origin access to other devices?
  * No, this API does not involve access to other devices.

* 3.11 - Does this specification allow an origin some measure of control over a
         user agent’s native UI?
  * No, this API does not involve access anything UI visible.

* 3.12 - Does this specification expose temporary identifiers to the web?
   * No, this API does not involve expose temporary identifiers.

* 3.13 - Does this specification distinguish between behavior in first-party and
         third-party contexts?
  * This API should behave identically to fetch in terms of first-party /
    third-party contexts.

* 3.14 - How should this specification work in the context of a user agent’s
         "incognito" mode?
  * This API should behave the same in incognito mode.

* 3.15 -  Does this specification persist data to a user’s local device?
  * Compilation is a strong hint for code caching, but does not mandate it.

* 3.16 - Does this specification have a "Security Considerations" and "Privacy
         Considerations" section?
  * The final WebAssembly spec will have these.

* 3.17 - Does this specification allow downgrading default security
         characteristics?
  * No it does not.
