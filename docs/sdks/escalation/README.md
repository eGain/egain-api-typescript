# Escalation
(*portal.escalation*)

## Overview

### Available Operations

* [startCustomerEscalation](#startcustomerescalation) - Start Customer Escalation
* [searchPriorToEscalation](#searchpriortoescalation) - Search Prior To Customer Escalation
* [completeCustomerEscalation](#completecustomerescalation) - Complete Customer Escalation
* [avertCustomerEscalation](#avertcustomerescalation) - Avert Customer Escalation

## startCustomerEscalation

## Overview
  The Start Escalation API is called to initiate an escalation and it must be called before any other escalation API. 
  An escalation occurs when a customer is referred to a higher level of support, such as chat or email, to address their issue. 
  This process is initiated when the initial support resources are insufficient by themselves. 

  Customer object is optional for authenticated customers. Values provided in request takes precedence over the values provided during customer registration.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="startCustomerEscalation" method="post" path="/portals/{portalID}/escalate" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.escalation.startCustomerEscalation({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    startEscalationRequest: {
      subject: "Issue with Product X",
      body: "I am experiencing an issue with Product X. Here are the details...\n" +
      "",
      channel: "email",
      url: "https://developerv3api.egain.cloud/system/templates/selfservice/oasis/help/customer/locale/en-us/portal/PROD-1002/escalate/search?q=help",
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
import { portalEscalationStartCustomerEscalation } from "@egain/egain-api-typescript/funcs/portalEscalationStartCustomerEscalation.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalEscalationStartCustomerEscalation(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    startEscalationRequest: {
      subject: "Issue with Product X",
      body: "I am experiencing an issue with Product X. Here are the details...\n" +
      "",
      channel: "email",
      url: "https://developerv3api.egain.cloud/system/templates/selfservice/oasis/help/customer/locale/en-us/portal/PROD-1002/escalate/search?q=help",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalEscalationStartCustomerEscalation failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.StartCustomerEscalationRequest](../../models/operations/startcustomerescalationrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.StartCustomerEscalationResponse](../../models/operations/startcustomerescalationresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## searchPriorToEscalation

## Overview
  The Search Prior to Customer Escalation API performs search on the subject and description parameters, but filters out any articles that the customer has viewed in the current session.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="searchPriorToEscalation" method="get" path="/portals/{portalID}/escalate/{escalationId}/search" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.escalation.searchPriorToEscalation({
    acceptLanguage: "en-US",
    portalID: "PROD-1002",
    escalationId: "6e1309ae-aef5-468a-9ff7-8c1f82a7c831",
    filterArticlesInTopicTree: "PROD-1066",
    additionalAttributes: "articleMacro",
    maxResults: 5,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalEscalationSearchPriorToEscalation } from "@egain/egain-api-typescript/funcs/portalEscalationSearchPriorToEscalation.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalEscalationSearchPriorToEscalation(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1002",
    escalationId: "6e1309ae-aef5-468a-9ff7-8c1f82a7c831",
    filterArticlesInTopicTree: "PROD-1066",
    additionalAttributes: "articleMacro",
    maxResults: 5,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalEscalationSearchPriorToEscalation failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.SearchPriorToEscalationRequest](../../models/operations/searchpriortoescalationrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleSearchResults](../../models/articlesearchresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## completeCustomerEscalation

## Overview
  The Complete Customer Escalation API allows customer to complete escalation and send an email to a customer service agent on behalf of the customer.

  After invoking the Complete Escalation or Avert Escalation APIs, the escalation ID associated with the escalation becomes invalid. 
  **Important:** Further attempts to use or reference the same escalation ID results in an error or failure.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="completeCustomerEscalation" method="put" path="/portals/{portalID}/escalate/{escalationId}/complete" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.escalation.completeCustomerEscalation({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    escalationId: "5d2b0881-9ef2-4c96-a4c2-b530f1ac306f",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalEscalationCompleteCustomerEscalation } from "@egain/egain-api-typescript/funcs/portalEscalationCompleteCustomerEscalation.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalEscalationCompleteCustomerEscalation(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    escalationId: "5d2b0881-9ef2-4c96-a4c2-b530f1ac306f",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalEscalationCompleteCustomerEscalation failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CompleteCustomerEscalationRequest](../../models/operations/completecustomerescalationrequest.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## avertCustomerEscalation

## Overview
  The Avert Customer Escalation API notifies the server that escalation to a live agent has been averted. Usually this means that the customer found the information they needed.

  After invoking the Complete Escalation or Avert Escalation APIs, the escalation ID associated with the escalation becomes invalid. 
  **Important:** Further attempts to use or reference the same escalation ID results in an error or failure.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="avertCustomerEscalation" method="put" path="/portals/{portalID}/escalate/{escalationId}/avert" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.escalation.avertCustomerEscalation({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    escalationId: "858789ed-672c-43dc-af37-e6a46d534ffe",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalEscalationAvertCustomerEscalation } from "@egain/egain-api-typescript/funcs/portalEscalationAvertCustomerEscalation.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalEscalationAvertCustomerEscalation(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    escalationId: "858789ed-672c-43dc-af37-e6a46d534ffe",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalEscalationAvertCustomerEscalation failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AvertCustomerEscalationRequest](../../models/operations/avertcustomerescalationrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |