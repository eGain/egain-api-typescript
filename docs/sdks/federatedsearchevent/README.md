# Federatedsearchevent
(*portal.federatedsearchevent*)

## Overview

### Available Operations

* [createFederatedSearchResultEvent](#createfederatedsearchresultevent) - Event For Viewed Federated Search Result

## createFederatedSearchResultEvent

## Overview
   The Federated Search Event API creates an event for federated search results that have been viewed.
  An event for viewing an: 
  * External web page cannot be created for a portal where the value for the "Include Web Search Section in Search Results" attribute is "Yes".
  * Internal web page cannot be created for a portal where the value for the "Include Intranet Search Section in Search Results" attribute is "Yes".


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createFederatedSearchResultEvent" method="post" path="/portals/{portalID}/search/federated/event" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.federatedsearchevent.createFederatedSearchResultEvent({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createFederatedSearchEvent: {
      q: "India",
      resultType: "external",
      url: "https://beetle.egain.com/",
      title: "Welcome to India",
      languageCode: "en-US",
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalFederatedsearcheventCreateFederatedSearchResultEvent } from "@egain/egain-api-typescript/funcs/portalFederatedsearcheventCreateFederatedSearchResultEvent.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalFederatedsearcheventCreateFederatedSearchResultEvent(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createFederatedSearchEvent: {
      q: "India",
      resultType: "external",
      url: "https://beetle.egain.com/",
      title: "Welcome to India",
      languageCode: "en-US",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalFederatedsearcheventCreateFederatedSearchResultEvent failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateFederatedSearchResultEventRequest](../../models/operations/createfederatedsearchresulteventrequest.md)                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |