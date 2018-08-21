---
description: HTTP status codes and response text returned by the Audience Management REST API.
seo-description: HTTP status codes and response text returned by the Audience Management REST API.
seo-title: Response Codes Defined
solution: Audience Manager
title: Response Codes Defined
uuid: 550df008-1de0-4235-acf7-839cc69f5746
index: y
internal: n
snippet: y
translate: y
---

# Response Codes Defined




>|  Response code ID  | Response text  | Definition  |
>|---|---|---|
>|  200  | OK  | The request processed successfully. Will return expected content or data if required.  |
>|  201  | Created  |The resource was created. Returns for ` PUT` and ` POST` requests.  |
>|  204  | No Content  | The resource has been deleted. The response body will be blank.  |
>|  400  | Bad Request  | The server did not understand the request. Usually due to malformed syntax. Check your request and try again.  |
>|  403  | Forbidden  | You do not have access to the resource.  |
>|  404  | Not Found  | The resource could not be found for the specified path.  |
>|  409  | Conflict  | The request could not be completed due to a conflict with the state of the resource.  |
>|  500  | Server Error  | The server encountered an unexpected error that prevented it from fulfilling the request.  |

