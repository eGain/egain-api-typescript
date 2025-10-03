# Retrieve
(*aiservices.retrieve*)

## Overview

### Available Operations

* [postPortalIDRetrieve](#postportalidretrieve) - Retrieve Chunks

## postPortalIDRetrieve

The Retrieve API enables enterprises to directly access relevant content chunks from their organizational knowledge sources. It is designed for scenarios where developers want granular control over retrieved information, such as powering custom search, analytics, or retrieval-augmented generation (RAG) pipelines. <br><br> In addition to raw chunk retrieval, the API can return **Certified Answers** if it meets the 'Certified Answer' threshold score. Responses include relevance scores, metadata, and references to maintain transparency and flexibility. By leveraging the Retrieve API, organizations can build tailored experiences while retaining confidence in the source material.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/{portalID}/retrieve" method="post" path="/{portalID}/retrieve" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.aiservices.retrieve.postPortalIDRetrieve({
    q: "mortgage rates",
    portalID: "PROD-1000",
    dollarFilterUserProfileID: "PROD-3210",
    language: "en-US",
    dollarFilterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    dollarFilterTopicIds: [
      "PROD-2000",
    ],
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { aiservicesRetrievePostPortalIDRetrieve } from "@egain/egain-api-typescript/funcs/aiservicesRetrievePostPortalIDRetrieve.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await aiservicesRetrievePostPortalIDRetrieve(egain, {
    q: "mortgage rates",
    portalID: "PROD-1000",
    dollarFilterUserProfileID: "PROD-3210",
    language: "en-US",
    dollarFilterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    dollarFilterTopicIds: [
      "PROD-2000",
    ],
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("aiservicesRetrievePostPortalIDRetrieve failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostPortalIDRetrieveRequest](../../models/operations/postportalidretrieverequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[models.RetrieveResponse](../../models/retrieveresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |