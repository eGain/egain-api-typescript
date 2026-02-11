# Topic
(*portal.topic*)

## Overview

### Available Operations

* [getTopicBreadcrumbForArticle](#gettopicbreadcrumbforarticle) - Get Topic Breadcrumb for Article
* [getchildtopics](#getchildtopics) - Get Immediate Child Topics
* [getancestortopics](#getancestortopics) - Get All Ancestor Topics
* [getalltopics](#getalltopics) - Get All Topics

## getTopicBreadcrumbForArticle

## Overview
  * Use this API to retrieve the topic breadcrumb for an article in a portal. A breadcrumb shows the hierarchical path from the root topic to the article's primary topic.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getTopicBreadcrumbForArticle" method="get" path="/portals/{portalID}/articles/{articleID}/breadcrumb" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.topic.getTopicBreadcrumbForArticle({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalTopicGetTopicBreadcrumbForArticle } from "@egain/egain-api-typescript/funcs/portalTopicGetTopicBreadcrumbForArticle.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalTopicGetTopicBreadcrumbForArticle(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalTopicGetTopicBreadcrumbForArticle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetTopicBreadcrumbForArticleRequest](../../models/operations/gettopicbreadcrumbforarticlerequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TopicBreadcrumb](../../models/topicbreadcrumb.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getchildtopics

## Overview
  The Get Immediate Child Topics API retrieves details about a topic and it's immediate child topics. The <code>$level</code> attribute determines how deep the topic hierarchy should go, or how many child topics of a topic are returned in the response.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getchildtopics" method="get" path="/portals/{portalID}/topics/{topicID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.topic.getchildtopics({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    topicID: "PROD-1069",
    level: -1,
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalTopicGetchildtopics } from "@egain/egain-api-typescript/funcs/portalTopicGetchildtopics.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalTopicGetchildtopics(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    topicID: "PROD-1069",
    level: -1,
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalTopicGetchildtopics failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetchildtopicsRequest](../../models/operations/getchildtopicsrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TopicTreeResult](../../models/topictreeresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getancestortopics

## Overview
  The Get All Ancestor Topics API retrieves the hierarchy from the root topic down to the given topic.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getancestortopics" method="get" path="/portals/{portalID}/topics/{topicID}/parents" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.topic.getancestortopics({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    topicID: "PROD-1069",
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalTopicGetancestortopics } from "@egain/egain-api-typescript/funcs/portalTopicGetancestortopics.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalTopicGetancestortopics(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    topicID: "PROD-1069",
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalTopicGetancestortopics failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetancestortopicsRequest](../../models/operations/getancestortopicsrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TopicResult](../../models/topicresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getalltopics

## Overview
  The Get All Topics API retrieves the topic tree for a portal. The <code>$level</code> attribute determines how deep the topic hierarchy should go, or how many child topics of a topic are returned in the response.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getalltopics" method="get" path="/portals/{portalID}/topics" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.topic.getalltopics({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    level: -1,
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalTopicGetalltopics } from "@egain/egain-api-typescript/funcs/portalTopicGetalltopics.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalTopicGetalltopics(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    level: -1,
    language: "en-US",
    topicAdditionalAttributes: [
      "modifiedBy.userName",
    ],
    customAdditionalAttributes: "country_name",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalTopicGetalltopics failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetalltopicsRequest](../../models/operations/getalltopicsrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TopicTreeResult](../../models/topictreeresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |