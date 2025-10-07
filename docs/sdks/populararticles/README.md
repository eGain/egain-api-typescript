# Populararticles
(*portal.populararticles*)

## Overview

### Available Operations

* [getpopulararticles](#getpopulararticles) - Get Popular Articles

## getpopulararticles

## Overview
  The Popular Articles API allows a user to retrieve popular articles. 
## Prerequisites 
    * Only displayable articles are returned. An Article is displayable when "Include in browse on portals" property is enable for the Article. 
## Permissions
  * Agent permissions: The following permissions are required if user is an Agent:
    * If Article has Access Tags, Article must be available for agent's current user profile.
    * If Article has Publish Views, at least one edition of Article must be available for agent's current user profile.
    * If Article has filters and tags query parameter provided, Article filters must match provided tags or tag groups.
  * Customer permissions: The following permissions are required if user is a Customer:              
      * If Article has Access tags: 
       * Portal must have default user profile, and;
       * Article must be available for portal's default user profile.
    * If Article has Publish Views:
      * Portal must have default user profile, and;
      * At least one edition must be available for portal's default user profile.
    *  If Article has filters and tags query parameter provided, Article filters must match provided tags or tag groups.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getpopulararticles" method="get" path="/portals/{portalID}/populararticles" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.populararticles.getpopulararticles({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterTopicId: "PROD-1067",
    language: "en-US",
    filterTags: "PROD-5381",
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
import { portalPopulararticlesGetpopulararticles } from "@egain/egain-api-typescript/funcs/portalPopulararticlesGetpopulararticles.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalPopulararticlesGetpopulararticles(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterTopicId: "PROD-1067",
    language: "en-US",
    filterTags: "PROD-5381",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalPopulararticlesGetpopulararticles failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetpopulararticlesRequest](../../models/operations/getpopulararticlesrequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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