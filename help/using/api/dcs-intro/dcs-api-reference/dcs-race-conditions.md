---
description: Describes how to prevent race conditions and DCS error handling.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Race Conditions and Error Handling
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
---
# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!DNL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!DNL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. A race condition is undesirable because it can corrupt or improperly overwrite cookie data. As a best practice, consider the following methods to help avoid this problem:

* Don't make simultaneous calls, or calls in rapid succession, to the [!DNL DCS] from the same user.
* Wait for each response to come back before making subsequent calls.

## Error Handling {#error-handling}

Error handling is limited for invalid or poorly formed queries. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!DNL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Opts out of tracking at the Audience Manager or partner level.
* Comes from an invalid/unselected geographic region.
* Disables browser cookies (either all or third-party).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
