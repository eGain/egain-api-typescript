# Suggestion
(*portal.suggestion*)

## Overview

### Available Operations

* [makeSuggestion](#makesuggestion) - Make a Suggestion
* [modifySuggestions](#modifysuggestions) - Modify Suggestion
* [searchSuggestion](#searchsuggestion) - Get Suggestion by Status
* [getSuggestion](#getsuggestion) - Get Suggestion by ID
* [deleteSuggestion](#deletesuggestion) - Delete a Suggestion
* [getRelatedArticlesForSuggestion](#getrelatedarticlesforsuggestion) - Get Related Articles for Suggestion
* [getSuggestionComments](#getsuggestioncomments) - Get Suggestion Comments
* [getSuggestionAttachments](#getsuggestionattachments) - Get Suggestion Attachments
* [getSuggestionAttachmentById](#getsuggestionattachmentbyid) - Get Suggestion Attachment by ID

## makeSuggestion

## Overview
  The Make a Suggestion API allows users to create an Article Suggestion from within a knowledge portal.

## Prerequisites
  * Enable the setting "Manage a Suggestion" for the portal specified in the URL.
  * If the user is a Customer, enable the setting "Allow Customer Access" for the portal.
  * If you want to add an attachment to a Suggestion, first call the Generate Signed URL to Upload API to add an attachment using the provided returned altID in attachment request.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="makeSuggestion" method="post" path="/portals/{portalID}/suggestions" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.suggestion.makeSuggestion({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createSuggestion: {
      name: "Proposed Store Phone Number",
      content: "You should update your website with the new phone number.",
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
import { portalSuggestionMakeSuggestion } from "@egain/egain-api-typescript/funcs/portalSuggestionMakeSuggestion.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionMakeSuggestion(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    createSuggestion: {
      name: "Proposed Store Phone Number",
      content: "You should update your website with the new phone number.",
      language: {
        code: "en-US",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalSuggestionMakeSuggestion failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.MakeSuggestionRequest](../../models/operations/makesuggestionrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## modifySuggestions

## Overview
  The Modify Suggestion API allows authenticated users to modify their own Suggestion.

## Prerequisites
  * Enable the setting "Manage a Suggestion" for the portal specified in the URL.
  * If the user is a Customer, enable the setting "Allow Customer Access" for the portal.
  * The "Suggestion ID" specified in the request body must exist and belong to the user.
  * The status of this Suggestion as returned by the Get Suggestion by ID API must be "pending".
  * At least one of the optional request body attributes must be provided.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="modifySuggestions" method="put" path="/portals/{portalID}/suggestions" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.suggestion.modifySuggestions({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    modifySuggestion: {
      id: "PROD-5722",
      name: "Improving Telecommunication Services",
      modifiedDate: "2024-07-31T14:10:19Z",
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionModifySuggestions } from "@egain/egain-api-typescript/funcs/portalSuggestionModifySuggestions.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionModifySuggestions(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    modifySuggestion: {
      id: "PROD-5722",
      name: "Improving Telecommunication Services",
      modifiedDate: "2024-07-31T14:10:19Z",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalSuggestionModifySuggestions failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ModifySuggestionsRequest](../../models/operations/modifysuggestionsrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## searchSuggestion

## Overview
  The Get Suggestion by Status API allows authenticated users to retrieve their own suggestions based on Suggestion status.
  
## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL.
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="searchSuggestion" method="get" path="/portals/{portalID}/suggestions" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.searchSuggestion({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterStatus: "suggested",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionSearchSuggestion } from "@egain/egain-api-typescript/funcs/portalSuggestionSearchSuggestion.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionSearchSuggestion(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterStatus: "suggested",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionSearchSuggestion failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.SearchSuggestionRequest](../../models/operations/searchsuggestionrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Suggestions](../../models/suggestions.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getSuggestion

## Overview
  The Get Suggestion by ID API allows authenticated users to retrieve their own suggestions.

## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL.
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The "Suggestion for the ID" specified in the URL must belong to the user.
 


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getSuggestion" method="get" path="/portals/{portalID}/suggestions/{suggestionID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.getSuggestion({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
    suggestionAdditionalAttributes: [
      "content",
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
import { portalSuggestionGetSuggestion } from "@egain/egain-api-typescript/funcs/portalSuggestionGetSuggestion.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionGetSuggestion(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
    suggestionAdditionalAttributes: [
      "content",
    ],
    customAdditionalAttributes: "country_name",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionGetSuggestion failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSuggestionRequest](../../models/operations/getsuggestionrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Suggestion](../../models/suggestion.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## deleteSuggestion

## Overview
  The Delete a Suggestion API allows authenticated users to delete their own Suggestion.

## Prerequisites
  * Enable the setting "Manage a Suggestion" for the portal specified in the URL.
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The Suggestion must belong to the user.
  * The status of the Suggestion must not be "approved".


### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteSuggestion" method="delete" path="/portals/{portalID}/suggestions/{suggestionID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.suggestion.deleteSuggestion({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionDeleteSuggestion } from "@egain/egain-api-typescript/funcs/portalSuggestionDeleteSuggestion.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionDeleteSuggestion(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalSuggestionDeleteSuggestion failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteSuggestionRequest](../../models/operations/deletesuggestionrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 401, 403, 404, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getRelatedArticlesForSuggestion

## Overview
  The Get Related Articles for Suggestion API allows authenticated users to retrieve related articles for a Suggestion.

## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL.
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The Suggestion specified in the URL must belong to the user.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getRelatedArticlesForSuggestion" method="get" path="/portals/{portalID}/suggestions/{suggestionID}/relatedArticles" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.getRelatedArticlesForSuggestion({
    acceptLanguage: "en-US",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionGetRelatedArticlesForSuggestion } from "@egain/egain-api-typescript/funcs/portalSuggestionGetRelatedArticlesForSuggestion.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionGetRelatedArticlesForSuggestion(egain, {
    acceptLanguage: "en-US",
    articleResultAdditionalAttributes: [
      "averageRating",
    ],
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionGetRelatedArticlesForSuggestion failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetRelatedArticlesForSuggestionRequest](../../models/operations/getrelatedarticlesforsuggestionrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.FeedbackArticleForSuggestion](../../models/feedbackarticleforsuggestion.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getSuggestionComments

## Overview
  The Get Suggestion Comments API allows authenticated users to retrieve all comments for a Suggestion.

## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL. 
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The Suggestion specified in the URL must belong to the user.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getSuggestionComments" method="get" path="/portals/{portalID}/suggestions/{suggestionID}/comments" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.getSuggestionComments({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionGetSuggestionComments } from "@egain/egain-api-typescript/funcs/portalSuggestionGetSuggestionComments.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionGetSuggestionComments(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionGetSuggestionComments failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSuggestionCommentsRequest](../../models/operations/getsuggestioncommentsrequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Comments](../../models/comments.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getSuggestionAttachments

## Overview
  The Get Suggestion Attachments API allows authenticated users to retrieve attachments for a Suggestion.

## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The Suggestion specified in the URL must belong to the user.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getSuggestionAttachments" method="get" path="/portals/{portalID}/suggestions/{suggestionID}/attachments" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.getSuggestionAttachments({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalSuggestionGetSuggestionAttachments } from "@egain/egain-api-typescript/funcs/portalSuggestionGetSuggestionAttachments.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionGetSuggestionAttachments(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    suggestionID: "PROD-11829",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionGetSuggestionAttachments failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSuggestionAttachmentsRequest](../../models/operations/getsuggestionattachmentsrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Attachments](../../models/attachments.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getSuggestionAttachmentById

## Overview
  The Get Suggestion Attachment by ID API allows authenticated users to get the details of an attachment that belongs to their own Suggestion. It also allows the download of attachment content. 

## Prerequisites
  * Enable the setting "My Suggestions" for the portal specified in the URL
  * If the user is a customer, enable the setting "Allow Customer Access" for the portal.
  * The Suggestion specified in the URL must belong to the user.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getSuggestionAttachmentById" method="get" path="/portals/{portalID}/suggestions/attachments/{attachmentID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.suggestion.getSuggestionAttachmentById({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    attachmentID: "PROD-1000",
    attachmentAdditionalAttributes: [
      "contentUrl",
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
import { portalSuggestionGetSuggestionAttachmentById } from "@egain/egain-api-typescript/funcs/portalSuggestionGetSuggestionAttachmentById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalSuggestionGetSuggestionAttachmentById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    attachmentID: "PROD-1000",
    attachmentAdditionalAttributes: [
      "contentUrl",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalSuggestionGetSuggestionAttachmentById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSuggestionAttachmentByIdRequest](../../models/operations/getsuggestionattachmentbyidrequest.md)                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.SuggestionAttachment](../../models/suggestionattachment.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |