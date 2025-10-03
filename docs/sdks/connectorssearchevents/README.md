# Connectorssearchevents
(*portal.connectorssearchevents*)

## Overview

### Available Operations

* [createSearchResultEventForConnectors](#createsearchresulteventforconnectors) - Event for Search Using Connectors
* [createViewedSearchResultsEventForConnectors](#createviewedsearchresultseventforconnectors) - Event for Viewed Search Results Using Connectors

## createSearchResultEventForConnectors

## Overview
   The Event for Search Using Connectors API creates an event to initiate a search operation for retrieving content from external sources or integrations within the portal. 
   It allows users to set up search events based on specified criteria.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createSearchResultEventForConnectors" method="post" path="/portals/{portalID}/search/connectors/event" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.connectorssearchevents.createSearchResultEventForConnectors({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createSearchResultEventForConnectors: {
      languageCode: "en-US",
      q: "India",
      numberOfSearchResults: 10,
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalConnectorssearcheventsCreateSearchResultEventForConnectors } from "@egain/egain-api-typescript/funcs/portalConnectorssearcheventsCreateSearchResultEventForConnectors.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalConnectorssearcheventsCreateSearchResultEventForConnectors(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createSearchResultEventForConnectors: {
      languageCode: "en-US",
      q: "India",
      numberOfSearchResults: 10,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalConnectorssearcheventsCreateSearchResultEventForConnectors failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateSearchResultEventForConnectorsRequest](../../models/operations/createsearchresulteventforconnectorsrequest.md)                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## createViewedSearchResultsEventForConnectors

## Overview
   The Event for Viewed Search Results Using Connectors API creates an event to log when search results from external content are viewed. 
   This helps in tracking and analyzing user interactions with search results retrieved from various external sources.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createViewedSearchResultsEventForConnectors" method="post" path="/portals/{portalID}/view/searchresults/connectors/event" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.connectorssearchevents.createViewedSearchResultsEventForConnectors({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createViewedSearchResultEventForConnectors: {
      languageCode: "en-US",
      q: "India",
      url: "https://beetle.egain.com/",
      title: "Welcome to India",
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors } from "@egain/egain-api-typescript/funcs/portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createViewedSearchResultEventForConnectors: {
      languageCode: "en-US",
      q: "India",
      url: "https://beetle.egain.com/",
      title: "Welcome to India",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateViewedSearchResultsEventForConnectorsRequest](../../models/operations/createviewedsearchresultseventforconnectorsrequest.md)                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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