# Wasm Response API Tag Questionnaire

Answers to questions
[here](https://www.w3.org/TR/security-privacy-questionnaire/).

* 3.1 - Does this specification deal with personally-identifiable information?
  * No personally-identifiable information is handled by this API.

* 3.2 - Does this specification deal with high-value data?
  * No high-value data is handled by this API.

* 3.3 - Does this specification introduce new state for an origin that persists
across browsing sessions?
  * Sort of. Explicit compilation provides a strong code caching hint.
    If honored strongly, this hint increases the likelihood that large amounts
    of code from an insecure origin (and thus a possibly compromised source),
    might persist.

    Browsers can mitigate this by tending not to persist with unfamiliar
    network interfaces.

    Even better, as we have done in Chrome, this API can be limited to secure
    origins only.


* 3.4 - Does this specification expose persistent, cross-origin state to the web?
  * No, although foreign fetch would cause 3.3 to affect cross-origin requests too.

* 3.5 - Does this specification expose any other data to an origin that it
doesn’t currently have access to?
  * By origin binding compilation, this API allows wasm modules accessed via a
    Content Security Policy that disallows unsafe-eval (which currently includes
    Wasm) to run.

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
