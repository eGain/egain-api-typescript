# General
(*portal.general*)

## Overview

### Available Operations

* [getAllPortals](#getallportals) - Get All Portals
* [getMyPortals](#getmyportals) - Get All Portals Accessible To User
* [getPortalDetailsById](#getportaldetailsbyid) - Get Portal Details By ID
* [getTagCategoriesForInterestForPortal](#gettagcategoriesforinterestforportal) - Get Tag Categories for Interest for a Portal

## getAllPortals

## Overview
  The Get All Portals API returns all portals in a partition or department.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAllPortals" method="get" path="/portals" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.general.getAllPortals({
    acceptLanguage: "en-US",
    departmentID: "999",
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
import { portalGeneralGetAllPortals } from "@egain/egain-api-typescript/funcs/portalGeneralGetAllPortals.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalGeneralGetAllPortals(egain, {
    acceptLanguage: "en-US",
    departmentID: "999",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGeneralGetAllPortals failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAllPortalsRequest](../../models/operations/getallportalsrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.PortalResult](../../models/portalresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getMyPortals

## Overview
  The Get All Portals Accessible to User API allows a user to fetch all portals accessible to user across all department.
  * If no access tags are specified for a portal, then any user can access the portal.
  * If access tags are specified for a portal, users with a user profile that allows access have access to the portal. For users with multiple user profiles, the user profile that allows access does not need to be the active user profile.
  * All the global users(partition) cannot be assigned user profiles; their access is limited to portals without access restrictions.
  * The only articles returned are associated to an Article type when the parameter, “Include in browse on portals” is set to "Yes".
  * When the "shortUrlTemplate" query parameter is provided, the API filters accessible portals according to the specified language and template name. Portal Short URL specific to to the "shortUrlTemplate" query parameter value is returned in the response.
  * When there is no short URL available for a specific language, the API returns a portal object with an empty "shortURL" field.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getMyPortals" method="get" path="/myportals" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.general.getMyPortals({
    acceptLanguage: "en-US",
    language: "en-US",
    department: "service",
    filterText: "master",
    shortUrlTemplate: "silver",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGeneralGetMyPortals } from "@egain/egain-api-typescript/funcs/portalGeneralGetMyPortals.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalGeneralGetMyPortals(egain, {
    acceptLanguage: "en-US",
    language: "en-US",
    department: "service",
    filterText: "master",
    shortUrlTemplate: "silver",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGeneralGetMyPortals failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetMyPortalsRequest](../../models/operations/getmyportalsrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.AllAccessiblePortals](../../models/allaccessibleportals.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getPortalDetailsById

## Overview
  The Get Portal Details By ID API allows a user to fetch details of a portal by the ID.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getPortalDetailsById" method="get" path="/portals/{portalID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.general.getPortalDetailsById({
    acceptLanguage: "en-US",
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
import { portalGeneralGetPortalDetailsById } from "@egain/egain-api-typescript/funcs/portalGeneralGetPortalDetailsById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalGeneralGetPortalDetailsById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGeneralGetPortalDetailsById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetPortalDetailsByIdRequest](../../models/operations/getportaldetailsbyidrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Portal](../../models/portal.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getTagCategoriesForInterestForPortal

## Overview
  The Get Tag Categories for Interest for a Portal API retrieves the Tag Categories for Interest configured for a portal.
  * Tag Categories are ordered in order of their addition in the "Tag Categories for Interest" in the Portal configuration.
  * Tags are ordered as per their order defined in their Tag Category.
  * Tag Groups are sorted by their name, in ascending order.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getTagCategoriesForInterestForPortal" method="get" path="/portals/{portalID}/tagcategoriesforinterest" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.general.getTagCategoriesForInterestForPortal({
    acceptLanguage: "en-US",
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
import { portalGeneralGetTagCategoriesForInterestForPortal } from "@egain/egain-api-typescript/funcs/portalGeneralGetTagCategoriesForInterestForPortal.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalGeneralGetTagCategoriesForInterestForPortal(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGeneralGetTagCategoriesForInterestForPortal failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetTagCategoriesForInterestForPortalRequest](../../models/operations/gettagcategoriesforinterestforportalrequest.md)                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TagCategoriesForInterest](../../models/tagcategoriesforinterest.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |