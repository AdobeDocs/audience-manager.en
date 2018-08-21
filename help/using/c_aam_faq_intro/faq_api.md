---
description: Common API questions and issues.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: API FAQ
uuid: e33b22e6-35a5-4e9b-8d99-dcee5d38a1cb
index: y
internal: n
snippet: y
translate: y
---

# API FAQ

The [ REST API](../c_api/c_rest_api_main/c_rest_api_main.md#concept_B512E6C3410A4304A672588A60A792B1) documentation contains details about specific methods and code samples. 

**Why does DIL make event calls with GET and POST methods?** 

DIL passes data to Audience Manager with a ` GET` or ` POST` method based on the length of the query string of the event call. This behavior is built in to ` GET` and ` POST` methods by default. It is not specific to [!DNL  Audience Manager]. 

* DIL makes event calls with ` GET` when a URL contains 2048 characters or less. A ` GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.
* DIL makes event calls with ` POST` when a URL contains more than 2048 characters. A ` POST` event call includes data in the body of the request. DIL puts data into key-value pairs and passes information as form data rather than in the URL query string.
Although each method passes data in a different way, this does not affect functionality. For example, with either method, Audience Manager still sends data to destinations, ID syncs works normally, and you can create traits from data signals. 

**What do the REST APIs allow me to do?** 

The REST APIs let you work programmatically with most Audience Management features and functions that are available in the user interface. 

**How do I obtain a REST API client ID and secret?** 

Contact your Partner Solutions representative to obtain API access credentials. Our APIs use [ OAuth 2.0](http://oauth.net/2/) standards for token authentication, authorization, and renewal. See [ OAuth Authentication](../c_api/c_rest_api_main/c_rest_api_overview/oauth-authentication.md#concept_426EEF5C102049B08C8ECF90FCB41796) for more information. 
