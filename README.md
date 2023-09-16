# URL Encoding in Boomi for HTTP Connector

Sometimes I've noticed that Boomi developers encounter error related to malformed URL while using Boomi's native HTTP connector, even though the endpoint is working from other API tools like Postman.

One of the reasons can be lack of URL encoding.

Boomi is primarily an iPaaS platform, so it doesn't have automatic URL Encoding feature yet. So, we have to explicitly perform URL Encoding while formulating the URL. This can be achieved by script, or, manually passing the encoded value such as %27 in place of single quote (').

I usually refer W3 Schools' URL encoding reference for manually passing the encoded values. Link - https://www.w3schools.com/tags/ref_urlencode.ASP  

Here, the Groovy script offers a more robust way of performing this URL encoding activity for the Boomi's native HTTP Connector, since we don't have to manually put all the required search/replace characters. Please refer the Groovy (2.4) script - "boomiUrlEncode.groovy", which can be used in Boomi as a **Map Script**.

However, the aforementioned Groovy script can encode the **space character** as **+** instead of ""%20**. In this case, please follow the below steps.

**Step-1:** Create a Map Function.

**Step-2:** String Replace the **space character** with **%20**.

**Step-3:** Use the Groovy (2.4) script - named "boomiUrlEncode.groovy".

**Step-4:** String Replace **%2520** with **%20**.

<img width="1186" alt="image" src="https://github.com/ayanpan/boomi-url-encode/assets/12267939/8f9d5329-6af6-4734-874f-33866c726556">
