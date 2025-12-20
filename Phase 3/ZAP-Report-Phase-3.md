# ZAP by Checkmarx Scanning Report

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 2 |
| Low | 5 |
| Informational | 1 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Content Security Policy (CSP) Header Not Set | Medium | 9 |
| Missing Anti-clickjacking Header | Medium | 9 |
| Server Leaks Version Information via "Server" HTTP Response Header Field | Low | 1 |
| Strict-Transport-Security Header Not Set | Low | 15 |
| Timestamp Disclosure - Unix | Low | 7 |
| X-Content-Type-Options Header Missing | Low | 10 |
| ZAP is Out of Date | Low | 9 |
| Re-examine Cache-control Directives | Informational | 9 |




## Alert Detail



### [ Content Security Policy (CSP) Header Not Set ](https://www.zaproxy.org/docs/alerts/10038/)



##### Medium (High)

### Description

Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696268326&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1728324084&target=OPTIMIZATION_TARGET_OMNIBOX_ON_DEVICE_TAIL_SUGGEST

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745311339&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745312779&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1761663972&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 9

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to set the Content-Security-Policy header.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP)
* [ https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
* [ https://www.w3.org/TR/CSP/ ](https://www.w3.org/TR/CSP/)
* [ https://w3c.github.io/webappsec-csp/ ](https://w3c.github.io/webappsec-csp/)
* [ https://web.dev/articles/csp ](https://web.dev/articles/csp)
* [ https://caniuse.com/#feat=contentsecuritypolicy ](https://caniuse.com/#feat=contentsecuritypolicy)
* [ https://content-security-policy.com/ ](https://content-security-policy.com/)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Missing Anti-clickjacking Header ](https://www.zaproxy.org/docs/alerts/10020/)



##### Medium (Medium)

### Description

The response does not protect against 'ClickJacking' attacks. It should include either Content-Security-Policy with 'frame-ancestors' directive or X-Frame-Options.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696268326&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1728324084&target=OPTIMIZATION_TARGET_OMNIBOX_ON_DEVICE_TAIL_SUGGEST

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745311339&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745312779&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1761663972&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 9

### Solution

Modern Web browsers support the Content-Security-Policy and X-Frame-Options HTTP headers. Ensure one of them is set on all web pages returned by your site/app.
If you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. Alternatively consider implementing Content Security Policy's "frame-ancestors" directive.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options)


#### CWE Id: [ 1021 ](https://cwe.mitre.org/data/definitions/1021.html)


#### WASC Id: 15

#### Source ID: 3

### [ Server Leaks Version Information via "Server" HTTP Response Header Field ](https://www.zaproxy.org/docs/alerts/10036/)



##### Low (High)

### Description

The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.

* URL: https://clientservices.googleapis.com/uma/v2

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `scaffolding on HTTPServer2`
  * Other Info: ``


Instances: 1

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to suppress the "Server" header or provide generic details.

### Reference


* [ https://httpd.apache.org/docs/current/mod/core.html#servertokens ](https://httpd.apache.org/docs/current/mod/core.html#servertokens)
* [ https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10) ](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10))
* [ https://www.troyhunt.com/shhh-dont-let-your-response-headers/ ](https://www.troyhunt.com/shhh-dont-let-your-response-headers/)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ Strict-Transport-Security Header Not Set ](https://www.zaproxy.org/docs/alerts/10035/)



##### Low (High)

### Description

HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTPS connections (i.e. HTTP layered over TLS/SSL). HSTS is an IETF standards track protocol and is specified in RFC 6797.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696268326&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1728324084&target=OPTIMIZATION_TARGET_OMNIBOX_ON_DEVICE_TAIL_SUGGEST

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745311339&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745312779&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1761663972&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://android.clients.google.com/c2dm/register3

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://android.clients.google.com/checkin

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://clientservices.googleapis.com/uma/v2

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://update.googleapis.com/service/update2/json%3Fcup2key=15:X3VAdZpK4kbwYohcuOCG7A4lGRwssqb1VPIzXV1Kk44&cup2hreq=e02d2070422a6e62568c14c2505b50c7871c0f3710092a76610d0d6e7bef388a

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://www.googleapis.com/chromewebstore/v1.1/items/verify

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 15

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to enforce Strict-Transport-Security.

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)
* [ https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security ](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
* [ https://caniuse.com/stricttransportsecurity ](https://caniuse.com/stricttransportsecurity)
* [ https://datatracker.ietf.org/doc/html/rfc6797 ](https://datatracker.ietf.org/doc/html/rfc6797)


#### CWE Id: [ 319 ](https://cwe.mitre.org/data/definitions/319.html)


#### WASC Id: 15

#### Source ID: 3

### [ Timestamp Disclosure - Unix ](https://www.zaproxy.org/docs/alerts/10096/)



##### Low (Low)

### Description

A timestamp was disclosed by the application/web server. - Unix

* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1673999601`
  * Other Info: `1673999601, which evaluates to: 2023-01-18 01:53:21.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1679317318`
  * Other Info: `1679317318, which evaluates to: 2023-03-20 15:01:58.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1696268326`
  * Other Info: `1696268326, which evaluates to: 2023-10-02 20:38:46.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1728324084`
  * Other Info: `1728324084, which evaluates to: 2024-10-07 21:01:24.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1745311339`
  * Other Info: `1745311339, which evaluates to: 2025-04-22 11:42:19.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1745312779`
  * Other Info: `1745312779, which evaluates to: 2025-04-22 12:06:19.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1761663972`
  * Other Info: `1761663972, which evaluates to: 2025-10-28 17:06:12.`


Instances: 7

### Solution

Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

### Reference


* [ https://cwe.mitre.org/data/definitions/200.html ](https://cwe.mitre.org/data/definitions/200.html)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ X-Content-Type-Options Header Missing ](https://www.zaproxy.org/docs/alerts/10021/)



##### Low (Medium)

### Description

The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696268326&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1728324084&target=OPTIMIZATION_TARGET_OMNIBOX_ON_DEVICE_TAIL_SUGGEST

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745311339&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745312779&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1761663972&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://clientservices.googleapis.com/uma/v2

  * Method: `POST`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`


Instances: 10

### Solution

Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.
If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.

### Reference


* [ https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85) ](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85))
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ ZAP is Out of Date ](https://www.zaproxy.org/docs/alerts/10116/)



##### Low (High)

### Description

The version of ZAP you are using to test your app is out of date and is no longer being updated.
The risk level is set based on how out of date your ZAP version is.

* URL: http://clients2.google.com/time/1/current%3Fcup2key=9:S_noDokBxOspkGFNBTgJ6s_0i34F0CWreugVnKc-rls&cup2hreq=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: http://localhost:8003/static/footer.js

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://www.google.com/async/folae%3Fasync=_fmt:pb

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://accounts.google.com/ListAccounts%3Fgpsia=1&source=ChromiumBrowser&json=standard&laf=b64bin

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://android.clients.google.com/checkin

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://clientservices.googleapis.com/uma/v2

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://update.googleapis.com/service/update2/json%3Fcup2key=15:X3VAdZpK4kbwYohcuOCG7A4lGRwssqb1VPIzXV1Kk44&cup2hreq=e02d2070422a6e62568c14c2505b50c7871c0f3710092a76610d0d6e7bef388a

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`
* URL: https://www.googleapis.com/chromewebstore/v1.1/items/verify

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`


Instances: 9

### Solution

Download the latest version of ZAP from https://www.zaproxy.org/download/ and install it.

### Reference


* [ https://www.zaproxy.org/download/ ](https://www.zaproxy.org/download/)


#### CWE Id: [ 1104 ](https://cwe.mitre.org/data/definitions/1104.html)


#### WASC Id: 45

#### Source ID: 3

### [ Re-examine Cache-control Directives ](https://www.zaproxy.org/docs/alerts/10015/)



##### Informational (Low)

### Description

The cache-control header has not been set properly or is missing, allowing the browser and proxies to cache content. For static assets like css, js, or image files this might be intended, however, the resources should be reviewed to ensure that no sensitive content will be cached.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696268326&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1728324084&target=OPTIMIZATION_TARGET_OMNIBOX_ON_DEVICE_TAIL_SUGGEST

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745311339&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1745312779&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1761663972&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=86400`
  * Other Info: ``


Instances: 9

### Solution

For secure content, ensure the cache-control HTTP header is set with "no-cache, no-store, must-revalidate". If an asset should be cached consider setting the directives "public, max-age, immutable".

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching ](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching)
* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cache-Control ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cache-Control)
* [ https://grayduck.mn/2021/09/13/cache-control-recommendations/ ](https://grayduck.mn/2021/09/13/cache-control-recommendations/)


#### CWE Id: [ 525 ](https://cwe.mitre.org/data/definitions/525.html)


#### WASC Id: 13

#### Source ID: 3


