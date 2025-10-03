# Article
(*portal.article*)

## Overview

### Available Operations

* [getArticleById](#getarticlebyid) - Get Article by ID
* [getArticleByIdWithEditions](#getarticlebyidwitheditions) - Get Article By ID with Editions
* [getArticleEditionDetails](#getarticleeditiondetails) - Get Article Edition Details
* [addToReply](#addtoreply) - Add Article to Reply
* [addAsReference](#addasreference) - Add as Reference
* [getArticlesInTopic](#getarticlesintopic) - Get Articles in Topic
* [getArticleAttachmentById](#getarticleattachmentbyid) - Get Article Attachment By ID
* [getAttachmentByIdInPortal](#getattachmentbyidinportal) - Get Article Attachment in Portal
* [getRelatedArticles](#getrelatedarticles) - Get Related Articles
* [getAnnouncementArticles](#getannouncementarticles) - Get Announcement Articles
* [getArticleRatings](#getarticleratings) - Get Article Ratings
* [rateArticle](#ratearticle) - Rate an Article
* [getPendingComplianceArticles](#getpendingcompliancearticles) - Get Pending Article Compliances
* [getAcknowledgedComplianceArticles](#getacknowledgedcompliancearticles) - Get Acknowledged Article Compliances
* [complyArticle](#complyarticle) - Comply With an Article
* [getMySubscription](#getmysubscription) - My Subscription
* [subscribeArticle](#subscribearticle) - Subscribe to an Article
* [unsubscribeArticle](#unsubscribearticle) - Unsubscribe to an Article
* [getArticlePermissionsById](#getarticlepermissionsbyid) - Get Article Permissions By ID
* [getArticlePersonalization](#getarticlepersonalization) - Get Article Personalization Details

## getArticleById

## Overview
  * The Get Article by ID API allows a user to retrieve an Article using its ID.
    * Additional Article attributes and contextual views can be specified in the query parameters.

  * This API returns structured authoring attributes of Issue, Environment, Cause and Confidence Level when the following conditions are met:
    * The "Allow Structured Authoring" setting is enabled at the partition/department level through the Administrative Console.
    * The "Use Structured Authoring" flag is set on the article type.

## Prerequisites
  * Agents without a user profile and customers in a portal without a default user profile only have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
  * Agents with a user profile and customers in a portal with a default user profile have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
    * Contain access tags that are also in the assigned user profiles.
    * Contain publish views with associated tags that are also in the assigned user profiles.
  * Agents with the following assigned actions can view updates to articles currently being processed in workflows:
    * View Author Portal – Allows agents to view updates to articles at any stage in a workflow.
    * View Staging Portal – Allows agents to view updates to articles in the Staging stage or a subsequent stage in a workflow.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticleById" method="get" path="/portals/{portalID}/articles/{articleID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticleById({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
    articleAdditionalAttributes: [
      "averageRating",
    ],
    customAdditionalAttributes: "country_name",
    publishViewId: "PROD-3203",
    workflowMilestone: "publish",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleGetArticleById } from "@egain/egain-api-typescript/funcs/portalArticleGetArticleById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticleById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
    articleAdditionalAttributes: [
      "averageRating",
    ],
    customAdditionalAttributes: "country_name",
    publishViewId: "PROD-3203",
    workflowMilestone: "publish",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticleById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticleByIdRequest](../../models/operations/getarticlebyidrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Article](../../models/article.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getArticleByIdWithEditions

## Overview
  * This API allows a user to retrieve an article with all its editions.
  * If there are no editions for the article, the response will contain the base content of the article.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticleByIdWithEditions" method="get" path="/articles/{articleID}/witheditions" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticleByIdWithEditions({
    acceptLanguage: "en-US",
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
import { portalArticleGetArticleByIdWithEditions } from "@egain/egain-api-typescript/funcs/portalArticleGetArticleByIdWithEditions.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticleByIdWithEditions(egain, {
    acceptLanguage: "en-US",
    articleID: "PROD-2996",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticleByIdWithEditions failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticleByIdWithEditionsRequest](../../models/operations/getarticlebyidwitheditionsrequest.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleWithEditions](../../models/articlewitheditions.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getArticleEditionDetails

## Overview
  * This API allows a user to retrieve an article with all its editions.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticleEditionDetails" method="get" path="/articles/{articleID}/editions/{publishViewId}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticleEditionDetails({
    acceptLanguage: "en-US",
    articleID: "PROD-2996",
    publishViewId: "959500000204621",
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
import { portalArticleGetArticleEditionDetails } from "@egain/egain-api-typescript/funcs/portalArticleGetArticleEditionDetails.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticleEditionDetails(egain, {
    acceptLanguage: "en-US",
    articleID: "PROD-2996",
    publishViewId: "959500000204621",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticleEditionDetails failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticleEditionDetailsRequest](../../models/operations/getarticleeditiondetailsrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.EditionWithContent](../../models/editionwithcontent.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## addToReply

## Overview
The Add Article to Reply API captures events for articles used in a reply for a digital channel activity.

Note:  Either the <code>x-ext-activity-id</code> or<br><code>x-ext-integration-id</code> and <code>x-ext-interaction-id</code> header must be provided.

## Permissions
  * Only Agents can invoke this API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="AddToReply" method="put" path="/portals/{portalID}/articles/{articleID}/addtoreply" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.addToReply({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    articleActivityLink: {
      versionId: "PROD-12416",
      editionId: "PROD-13015",
      language: {
        code: "en-US",
      },
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleAddToReply } from "@egain/egain-api-typescript/funcs/portalArticleAddToReply.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleAddToReply(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    articleActivityLink: {
      versionId: "PROD-12416",
      editionId: "PROD-13015",
      language: {
        code: "en-US",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleAddToReply failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AddToReplyRequest](../../models/operations/addtoreplyrequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## addAsReference

## Overview
The Add as Reference API captures events for articles that are referenced by agents replying inside of a digital channel activity.

Note: Either the <code>x-ext-activity-id</code> or<br><code>x-ext-integration-id</code> and <code>x-ext-interaction-id</code> header must be provided.

## Permissions
  * Only Agents can invoke this API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="AddAsReference" method="put" path="/portals/{portalID}/articles/{articleID}/addasreference" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.addAsReference({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    articleActivityLink: {
      versionId: "PROD-12416",
      editionId: "PROD-13015",
      language: {
        code: "en-US",
      },
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleAddAsReference } from "@egain/egain-api-typescript/funcs/portalArticleAddAsReference.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleAddAsReference(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    articleActivityLink: {
      versionId: "PROD-12416",
      editionId: "PROD-13015",
      language: {
        code: "en-US",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleAddAsReference failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AddAsReferenceRequest](../../models/operations/addasreferencerequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## getArticlesInTopic

## Overview
The Get Articles in Topic API allows a user to retrieve the browsable articles in a topic.

## Prerequisites
  * Set the Article type’s parameter “Include in browse on portals” to "Yes" for an article to be returned by this API.
  * Agents without a user profile and customers in a portal without a default user profile only have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain published views without any associated tags.
  * Agents with a user profile and customers in a portal with a default user profile have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
    * Contain access tags that are also in the assigned user profiles.
    * Contain publish views with associated tags that are also in the assigned user profiles.
  
## Permissions  
  * Agents with the following assigned actions can view updates to articles currently being processed in workflows:
    * View Author Portal – Allows agents to view updates to articles at any stage in a workflow.
    * View Staging Portal – Allows agents to view updates to articles in the Staging stage or a subsequent stage in a workflow.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticlesInTopic" method="get" path="/portals/{portalID}/articles" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticlesInTopic({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    dollarFilterTopicId: "PROD-1065",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    dollarFilterTags: "PROD-5381",
    workflowMilestone: "publish",
    language: "en-US",
    sort: "name",
    order: "asc",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleGetArticlesInTopic } from "@egain/egain-api-typescript/funcs/portalArticleGetArticlesInTopic.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticlesInTopic(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    searchProfileId: "959500000204621",
    dollarFilterTopicId: "PROD-1065",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    dollarFilterTags: "PROD-5381",
    workflowMilestone: "publish",
    language: "en-US",
    sort: "name",
    order: "asc",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticlesInTopic failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticlesInTopicRequest](../../models/operations/getarticlesintopicrequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleResults](../../models/articleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getArticleAttachmentById

## Overview
  This API allows one article attachment identified by an attachment ID to be retrieved.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticleAttachmentById" method="get" path="/articles/attachments/{attachmentID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticleAttachmentById({
    acceptLanguage: "en-US",
    attachmentID: "PROD-1000",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleGetArticleAttachmentById } from "@egain/egain-api-typescript/funcs/portalArticleGetArticleAttachmentById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticleAttachmentById(egain, {
    acceptLanguage: "en-US",
    attachmentID: "PROD-1000",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticleAttachmentById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticleAttachmentByIdRequest](../../models/operations/getarticleattachmentbyidrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.AttachmentContentResult](../../models/attachmentcontentresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getAttachmentByIdInPortal

## Overview
The Get Article Attachment API retrieves an attachment associated to an article by calling the attachment ID for a specified portal ID.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAttachmentByIdInPortal" method="get" path="/portals/{portalID}/articles/attachments/{attachmentID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getAttachmentByIdInPortal({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    attachmentID: "PROD-1000",
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
import { portalArticleGetAttachmentByIdInPortal } from "@egain/egain-api-typescript/funcs/portalArticleGetAttachmentByIdInPortal.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetAttachmentByIdInPortal(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    attachmentID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetAttachmentByIdInPortal failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAttachmentByIdInPortalRequest](../../models/operations/getattachmentbyidinportalrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.AttachmentContentResult](../../models/attachmentcontentresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getRelatedArticles

## Overview
The Get Related Articles API retrieves all related articles associated to a given article.

## Prerequisites
  * Set the Article type’s parameter “Include in browse on portals” to "Yes" for an article to be returned by this API.
  * Agents without a user profile and customers in a portal without a default user profile only have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
  * Agents with a user profile and customers in a portal with a default user profile have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
    * Contain access tags that are also in the assigned user profiles.
    * Contain publish views with associated tags that are also in the assigned user profiles.

## Permissions 
  * Agents with the following assigned actions can view updates to articles currently being processed in workflows:
    * View Author Portal – Allows agents to view updates to articles at any stage in a workflow.
    * View Staging Portal – Allows agents to view updates to articles in the Staging stage or a subsequent stage in a workflow.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getRelatedArticles" method="get" path="/portals/{portalID}/articles/{articleID}/related" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getRelatedArticles({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    dollarFilterTags: "PROD-5381",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    workflowMilestone: "publish",
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
import { portalArticleGetRelatedArticles } from "@egain/egain-api-typescript/funcs/portalArticleGetRelatedArticles.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetRelatedArticles(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    dollarFilterTags: "PROD-5381",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    workflowMilestone: "publish",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetRelatedArticles failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetRelatedArticlesRequest](../../models/operations/getrelatedarticlesrequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleResults](../../models/articleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getAnnouncementArticles

## Overview
The Get Announcement Articles API returns a portal's announcement articles. Only displayable announcement articles in the portal are returned. 

## Prerequisites
  * For an article to display or be returned, set the Article type’s parameter, “Include in browse on portals,” to "Yes".
  * Agents without a user profile and customers in a portal without a default user profile only have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
  * Agents with a user profile and customers in a portal with a default user profile have access to articles that:
    * Do not contain any access tags.
    * Do not contain any publish views.
    * Contain publish views without any associated tags.
    * Contain access tags that are also in the assigned user profiles.
    * Contain publish views with associated tags that are also in the assigned user profiles.

## Permissions 
  * Agents with the following assigned actions can view updates to articles currently being processed in workflows:
    * View Author Portal – Allows agents to view updates to articles at any stage in a workflow.
    * View Staging Portal – Allows agents to view updates to articles in the Staging stage or a subsequent stage in a workflow.
    


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAnnouncementArticles" method="get" path="/portals/{portalID}/articles/announcements" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getAnnouncementArticles({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    dollarFilterTags: "PROD-5381",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    workflowMilestone: "publish",
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
import { portalArticleGetAnnouncementArticles } from "@egain/egain-api-typescript/funcs/portalArticleGetAnnouncementArticles.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetAnnouncementArticles(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    dollarFilterTags: "PROD-5381",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    workflowMilestone: "publish",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetAnnouncementArticles failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAnnouncementArticlesRequest](../../models/operations/getannouncementarticlesrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleResults](../../models/articleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getArticleRatings

## Overview
The Get Article Ratings API returns ratings set for an Article. These ratings help you to assess the quality, helpfulness, or relevance of an article. 


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticleRatings" method="get" path="/portals/{portalID}/articles/{articleID}/ratings" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticleRatings({
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
import { portalArticleGetArticleRatings } from "@egain/egain-api-typescript/funcs/portalArticleGetArticleRatings.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticleRatings(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticleRatings failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticleRatingsRequest](../../models/operations/getarticleratingsrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleRatingsResponse](../../models/articleratingsresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## rateArticle

## Overview
The Rate an Article API allows a user to set a rating for an article. These ratings allow you to assess the quality, helpfulness, or relevance of an article. 


### Example Usage

<!-- UsageSnippet language="typescript" operationID="rateArticle" method="put" path="/portals/{portalID}/articles/{articleID}/ratings" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.rateArticle({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
    score: 10,
    comments: "Accepted",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleRateArticle } from "@egain/egain-api-typescript/funcs/portalArticleRateArticle.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleRateArticle(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
    score: 10,
    comments: "Accepted",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleRateArticle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RateArticleRequest](../../models/operations/ratearticlerequest.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## getPendingComplianceArticles

## Overview
The Get Pending Article Compliances API retrieves all compliance-enabled articles in a portal that need to be read by the current user. Results are sorted in ascending order of the compliance due date.

## Prerequisites
* The Article compliances that are returned must be:
    * Available for the current user profile.
    * Displayable. An article is displayable when the "Include in browse on portals" property is enabled for the article.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getPendingComplianceArticles" method="get" path="/portals/{portalID}/articles/compliance/pending" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getPendingComplianceArticles({
    acceptLanguage: "en-US",
    complianceArticleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
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
import { portalArticleGetPendingComplianceArticles } from "@egain/egain-api-typescript/funcs/portalArticleGetPendingComplianceArticles.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetPendingComplianceArticles(egain, {
    acceptLanguage: "en-US",
    complianceArticleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetPendingComplianceArticles failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetPendingComplianceArticlesRequest](../../models/operations/getpendingcompliancearticlesrequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ComplianceArticleResults](../../models/compliancearticleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getAcknowledgedComplianceArticles

## Overview
The Get Acknowledged Article Compliances API retrieves all compliance-enabled articles in a portal that have been read by the current user in the last 60 days. Results are sorted in descending order of the acknowledgement date.

## Prerequisites
* The Article compliances that are returned must be:
    * Available for the current user profile.
    * Displayable. An article is displayable when the "Include in browse on portals" property is enabled for the article.
    * Acknowledged within the last 60 days.
    * Only the latest version of a republished compliance article will be shown.
    * Results will be sorted in descending order of acknowledgment date.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAcknowledgedComplianceArticles" method="get" path="/portals/{portalID}/articles/compliance/acknowledged" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getAcknowledgedComplianceArticles({
    acceptLanguage: "en-US",
    complianceArticleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
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
import { portalArticleGetAcknowledgedComplianceArticles } from "@egain/egain-api-typescript/funcs/portalArticleGetAcknowledgedComplianceArticles.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetAcknowledgedComplianceArticles(egain, {
    acceptLanguage: "en-US",
    complianceArticleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetAcknowledgedComplianceArticles failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAcknowledgedComplianceArticlesRequest](../../models/operations/getacknowledgedcompliancearticlesrequest.md)                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ComplianceArticleResults](../../models/compliancearticleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## complyArticle

## Overview
The Comply with an Article API allows the user to comply with an article by passing the Article's ID, which marks it as read by the user.            

## Prerequisites
  * The user must be an agent and:
    * Be available in the portal.
    * Be available for the current user profile.
    * Have the Article's compliance policy enabled.
  * If the Article has Access Tags, then it must be available for the agent's current user profile.
  * If the Article has Publish Views, then at least one edition of the Article must be available for the agent's current user profile.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="complyArticle" method="put" path="/portals/{portalID}/articles/{articleID}/comply" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.complyArticle({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleComplyArticle } from "@egain/egain-api-typescript/funcs/portalArticleComplyArticle.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleComplyArticle(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleComplyArticle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ComplyArticleRequest](../../models/operations/complyarticlerequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## getMySubscription

## Overview
The My Subscription API allows authenticated users and agents to retrieve the list of articles to which they are subscribed.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getMySubscription" method="get" path="/portals/{portalID}/articles/subscribed" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getMySubscription({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    workflowMilestone: "publish",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleGetMySubscription } from "@egain/egain-api-typescript/funcs/portalArticleGetMySubscription.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetMySubscription(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    workflowMilestone: "publish",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetMySubscription failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetMySubscriptionRequest](../../models/operations/getmysubscriptionrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticleResults](../../models/articleresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## subscribeArticle

## Overview
The Subscribe to an Article API allows eGain users, authenticated customers and agents to subscribe and receive notifications about changes to an Article.

## Prerequisites
  * Notifications are sent only if the following conditions are met:
    * The Article content has been modified since the last published version.
    * The attachment list has been modified since the last published version.
    * The author has checked the "Include Article in new and modified Article list" option while publishing the Article.
  * For the Subscribe to an Article API to execute successfully:
    * The Article must be in the portal.
    * The user must have provided an email address.

## Permissions
  * Agent Permissions: The following permissions are required if the user is an agent:
    * If the Article has Access Tags:
      * The Article must be available for the agent's current user profile.
    * If the Article has Publish Views:
      * At least one edition of the Article must be available for the agent's current user profile.
    * If the Article has filters and the "tags query parameter" is provided:
      * The Article filters must match the provided tags or tag groups.
  * Customer Permissions: The following permissions are required if the user is a customer:
    * If the Article has Access Tags:
      * The portal must have a default user profile
      * The Article must be available for the portal's default user profile.
    * If the Article has Publish Views:
      * The portal must have a default user profile
      * At least one edition must be available for the portal's default user profile.
    * If the Article has filters and the "tags query parameter" is provided, then the Article filters must match the provided tags or tag groups.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="subscribeArticle" method="put" path="/portals/{portalID}/articles/{articleID}/subscribe" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.subscribeArticle({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleSubscribeArticle } from "@egain/egain-api-typescript/funcs/portalArticleSubscribeArticle.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleSubscribeArticle(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleSubscribeArticle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.SubscribeArticleRequest](../../models/operations/subscribearticlerequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## unsubscribeArticle

## Overview
The Unsubscribe to an Article API allows authenticated users and agents to unsubscribe to an Article for which they were earlier subscribed to receive change notifications.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="unsubscribeArticle" method="put" path="/portals/{portalID}/articles/{articleID}/unsubscribe" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.article.unsubscribeArticle({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleUnsubscribeArticle } from "@egain/egain-api-typescript/funcs/portalArticleUnsubscribeArticle.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleUnsubscribeArticle(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalArticleUnsubscribeArticle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UnsubscribeArticleRequest](../../models/operations/unsubscribearticlerequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## getArticlePermissionsById

## Overview
  * The Get Article Permission by ID permits a user to retrieve permissions associated to an article.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticlePermissionsById" method="get" path="/portals/{portalID}/articles/{articleID}/permissions" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticlePermissionsById({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalArticleGetArticlePermissionsById } from "@egain/egain-api-typescript/funcs/portalArticleGetArticlePermissionsById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticlePermissionsById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticlePermissionsById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticlePermissionsByIdRequest](../../models/operations/getarticlepermissionsbyidrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ArticlePermissionsResult](../../models/articlepermissionsresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getArticlePersonalization

## Overview
  The Get Article Personalization Details API allows agents to retrieve the personalization tag details of an Article.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getArticlePersonalization" method="get" path="/portals/{portalID}/articles/{articleID}/personalization" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.article.getArticlePersonalization({
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
import { portalArticleGetArticlePersonalization } from "@egain/egain-api-typescript/funcs/portalArticleGetArticlePersonalization.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalArticleGetArticlePersonalization(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    articleID: "PROD-2996",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalArticleGetArticlePersonalization failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetArticlePersonalizationRequest](../../models/operations/getarticlepersonalizationrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Personalization](../../models/personalization.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |