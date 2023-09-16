# URL Encoding in Boomi for HTTP Connector

Sometimes I've noticed that Boomi developers encounter error related to malformed URL while using Boomi's native HTTP connector, even though the endpoint is working from other API tools like Postman.

One of the reasons can be lack of URL encoding.

Boomi is primarily an iPaaS platform, so it doesn't have automatic URL Encoding feature yet. So, we have to explicitly perform URL Encoding while formulating the URL. This can be achieved by script, or, manually passing the encoded value such as %27 in place of single quote (').

I usually refer W3 Schools' URL encoding reference for manually passing the encoded values. Link - https://www.w3schools.com/tags/ref_urlencode.ASP  

Here, the Groovy script offers a more robust way of performing this URL encoding activity for the Boomi's native HTTP Connector, since we don't have to manually put all the required search/replace characters. Please refer the Groovy (2.4) script named "boomiUrlEncode.groovy".
