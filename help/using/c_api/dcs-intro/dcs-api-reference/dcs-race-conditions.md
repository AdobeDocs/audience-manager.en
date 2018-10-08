---
description: Describes how to prevent race conditions and DCS error handling.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Race Conditions and Error Handling
uuid: f5844509-8b5b-45f8-b39b-2a4026d20c69
index: y
internal: n
snippet: y
translate: y
---

# Race Conditions and Error Handling

Describes how to prevent race conditions and DCS error handling.

## Preventing Race Conditions {#section_0F9D28831F6243A3B174450DD1B9635D}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. A race condition is undesirable because it can corrupt or improperly overwrite cookie data. As a best practice, consider the following methods to help avoid this problem:

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user. 
* Wait for each response to come back before making subsequent calls.

## Error Handling {#section_BA7880213216436B835884E753710AC4}

Error handling is limited for invalid or poorly formed queries. An invalid request returns an HTTP 200 OK response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an HTTP 200 OK response when a user:

* Opts out of tracking at the Audience Manager or partner level. 
* Comes from an invalid/unselected geographic region. 
* Disables browser cookies (either all or third-party).

See also, [DCS Error Codes, Messages, and Examples](../../../c_api/dcs-intro/dcs-api-reference/dcs_error_codes.md#reference_8C64917F3A584F61BF3B908F8129DE5F). 
