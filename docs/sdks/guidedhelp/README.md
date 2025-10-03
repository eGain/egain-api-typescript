# Guidedhelp
(*portal.guidedhelp*)

## Overview

### Available Operations

* [getAllCasebasesReleases](#getallcasebasesreleases) - Get Available Casebases Releases
* [getCasebaseReleaseById](#getcasebasereleasebyid) - Get Details of a Casebase Release
* [getClusterByCasebaseReleaseId](#getclusterbycasebasereleaseid) - Get Cluster Details of a Casebase Release
* [getAllProfilesInPortal](#getallprofilesinportal) - Get All Profiles Available in Portal
* [startGHSearch](#startghsearch) - Start a Guided Help Search
* [stepGHSearch](#stepghsearch) - Perform a Step in a Guided Help Search
* [getAllCases](#getallcases) - Get All Cases of a Cluster in Release
* [getCaseById](#getcasebyid) - Get Details of a Case
* [acceptGHSolution](#acceptghsolution) - Accept Solution
* [rejectGHSolution](#rejectghsolution) - Reject Solution
* [createQuickpick](#createquickpick) - Create Quickpick
* [getAllQuickPicks](#getallquickpicks) - Get All Quickpicks for a Portal
* [restoreQuickpick](#restorequickpick) - Resume a Quickpick

## getAllCasebasesReleases

## Overview
  The Get Available Casebases Releases API retrieves all Casebase Releases associated with a portal.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAllCasebasesReleases" method="get" path="/portals/{portalID}/gh/casebasereleases" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getAllCasebasesReleases({
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
import { portalGuidedhelpGetAllCasebasesReleases } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetAllCasebasesReleases.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetAllCasebasesReleases(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetAllCasebasesReleases failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAllCasebasesReleasesRequest](../../models/operations/getallcasebasesreleasesrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.CasebaseResult](../../models/casebaseresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getCasebaseReleaseById

## Overview
  The Get Details of a Casebase Release API retrieves details of Casebase Release.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getCasebaseReleaseById" method="get" path="/portals/{portalID}/gh/casebasereleases/{casebaseReleaseID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getCasebaseReleaseById({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
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
import { portalGuidedhelpGetCasebaseReleaseById } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetCasebaseReleaseById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetCasebaseReleaseById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetCasebaseReleaseById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetCasebaseReleaseByIdRequest](../../models/operations/getcasebasereleasebyidrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.CasebaseResult](../../models/casebaseresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getClusterByCasebaseReleaseId

## Overview
  The Get Cluster Details of a Casebase Release API retrieves cluster details of Casebase Release.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getClusterByCasebaseReleaseId" method="get" path="/portals/{portalID}/gh/casebasereleases/{casebaseReleaseID}/clusters" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getClusterByCasebaseReleaseId({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
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
import { portalGuidedhelpGetClusterByCasebaseReleaseId } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetClusterByCasebaseReleaseId.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetClusterByCasebaseReleaseId(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetClusterByCasebaseReleaseId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetClusterByCasebaseReleaseIdRequest](../../models/operations/getclusterbycasebasereleaseidrequest.md)                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ClusterResults](../../models/clusterresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getAllProfilesInPortal

## Overview
  The Get All Profiles Available in Portal API retrieves all Guided Help profiles associated with a portal.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAllProfilesInPortal" method="get" path="/portals/{portalID}/gh/profiles" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getAllProfilesInPortal({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterCasebaseRelease: "202201000000002",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGuidedhelpGetAllProfilesInPortal } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetAllProfilesInPortal.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetAllProfilesInPortal(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    filterCasebaseRelease: "202201000000002",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetAllProfilesInPortal failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAllProfilesInPortalRequest](../../models/operations/getallprofilesinportalrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ProfileResult](../../models/profileresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## startGHSearch

## Overview
   The Start a Guided Help search can be used to start a search session in the Guided Help. 
   
   A Guided Help profile can also be specified while starting the session and it is used to filter the results of search.
   If this is not passed in the request, the default profile of the portal is used. Questions can also be answered at time of starting the search session. 
   
   A Guided Help search session can be started in following ways:
   * Launch session for a specific Casebase Release.
   * Launch session for a Casebase and specify the release type.
   * Use a Guided Help session Article and pass the required session parameters.

## Prerequisites
   * A Guided Help profile must be assigned to the user.
   * Casebase Release passed in the request must be associated with the portal passed in URI. 
   


### Example Usage

<!-- UsageSnippet language="typescript" operationID="startGHSearch" method="post" path="/portals/{portalID}/gh/search" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.startGHSearch({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
    ghSearchRequest: {
      casebaseId: "202201000000002",
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
import { portalGuidedhelpStartGHSearch } from "@egain/egain-api-typescript/funcs/portalGuidedhelpStartGHSearch.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpStartGHSearch(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
    ghSearchRequest: {
      casebaseId: "202201000000002",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpStartGHSearch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.StartGHSearchRequest](../../models/operations/startghsearchrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.StartGHSearchResponse](../../models/operations/startghsearchresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 429                      | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## stepGHSearch

## Overview
   The Perform a Step in a Guided Help Search API can be used to answer one or more questions (perform a step) in Guided Help search.

## Prerequisites
   * A Guided Help session must be in progress before this API is invoked.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="stepGHSearch" method="put" path="/portals/{portalID}/gh/search" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.stepGHSearch({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
    ghStepSearchRequest: {
      casebaseId: "202201000000002",
      questions: [
        {
          id: "1000000322",
          answers: [
            {
              id: "1000000303",
            },
          ],
        },
        {
          id: "1000000327",
          answers: [
            {
              id: "1000000842",
            },
          ],
        },
        {
          id: "1000001006",
          answers: [
            {
              id: "1000001001",
            },
          ],
        },
      ],
      useLiveRelease: true,
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
import { portalGuidedhelpStepGHSearch } from "@egain/egain-api-typescript/funcs/portalGuidedhelpStepGHSearch.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpStepGHSearch(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
    ghStepSearchRequest: {
      casebaseId: "202201000000002",
      questions: [
        {
          id: "1000000322",
          answers: [
            {
              id: "1000000303",
            },
          ],
        },
        {
          id: "1000000327",
          answers: [
            {
              id: "1000000842",
            },
          ],
        },
        {
          id: "1000001006",
          answers: [
            {
              id: "1000001001",
            },
          ],
        },
      ],
      useLiveRelease: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpStepGHSearch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.StepGHSearchRequest](../../models/operations/stepghsearchrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.GHSearchResult](../../models/ghsearchresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getAllCases

## Overview
  The Get All Cases of a Cluster in Release API retrieves all cases in cluster of a Casebase Release. A Case is a group of Questions, Articles, and control actions that work together to guide users through a series of questions and scenarios in a Guided Help session.  

## Prerequisites
  A Guided Help search session for the provided Casebase Release must be in progress before this API is invoked.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAllCases" method="get" path="/portals/{portalID}/gh/casebasereleases/{casebaseReleaseID}/clusters/{clusterID}/cases" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getAllCases({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    clusterID: "1000000402",
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
import { portalGuidedhelpGetAllCases } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetAllCases.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetAllCases(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    clusterID: "1000000402",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetAllCases failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAllCasesRequest](../../models/operations/getallcasesrequest.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.CaseListResults](../../models/caselistresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## getCaseById

## Overview
  The Get Details of a Case API retrieves details of a case in a release.

## Prerequisites
  * A Guided Help search session for the provided Casebase Release must be in progress before this API is invoked.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getCaseById" method="get" path="/portals/{portalID}/gh/casebasereleases/{casebaseReleaseID}/cases/{caseID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getCaseById({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    caseID: "1000001085",
    language: "en-US",
    caseAdditionalAttributes: [
      "actions",
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
import { portalGuidedhelpGetCaseById } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetCaseById.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetCaseById(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    casebaseReleaseID: "202201000000002",
    caseID: "1000001085",
    language: "en-US",
    caseAdditionalAttributes: [
      "actions",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetCaseById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetCaseByIdRequest](../../models/operations/getcasebyidrequest.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Case](../../models/case.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## acceptGHSolution

## Overview
  The Accept Solution API can be used to accept and add positive score to a solution of a Guided Help case.

## Prerequisites
   * A Guided Help search session must be started before invoking this API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="acceptGHSolution" method="post" path="/portals/{portalID}/gh/cases/{caseID}/accept" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.guidedhelp.acceptGHSolution({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    caseID: "1000001085",
    quickpickRating: {
      id: "120000001201010",
      name: "HPE Solution Article",
      profileId: "120450120000001",
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGuidedhelpAcceptGHSolution } from "@egain/egain-api-typescript/funcs/portalGuidedhelpAcceptGHSolution.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpAcceptGHSolution(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    caseID: "1000001085",
    quickpickRating: {
      id: "120000001201010",
      name: "HPE Solution Article",
      profileId: "120450120000001",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalGuidedhelpAcceptGHSolution failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AcceptGHSolutionRequest](../../models/operations/acceptghsolutionrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## rejectGHSolution

## Overview
  The Reject Solution API can be used to reject and add negative score to a solution of a Guided Help case.

## Prerequisites
   * A Guided Help search session must be started before invoking this API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="rejectGHSolution" method="post" path="/portals/{portalID}/gh/cases/{caseID}/reject" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.guidedhelp.rejectGHSolution({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    caseID: "1000001085",
    quickpickRating: {
      id: "123101210000102",
      name: "HPE Solution Article",
      profileId: "100101210000002",
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGuidedhelpRejectGHSolution } from "@egain/egain-api-typescript/funcs/portalGuidedhelpRejectGHSolution.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpRejectGHSolution(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    caseID: "1000001085",
    quickpickRating: {
      id: "123101210000102",
      name: "HPE Solution Article",
      profileId: "100101210000002",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalGuidedhelpRejectGHSolution failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RejectGHSolutionRequest](../../models/operations/rejectghsolutionrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## createQuickpick

## Overview
   The Create Quickpick API can be used to create a new quickpick(bookmark) for current Guided Help search session.

  Note: If "linkToActivity" attribute is passed as true in request body then one of below must be passed in header
   * <code>XEgainTenantId</code>
   * <code>xEgainActivityId</code>
   * <code>XInteractionId</code>

## Prerequisites
   * A Guided Help search session must be in progress before this API is invoked.
   * QuickPick can only be created for a live release of a Casebase.
   


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createQuickpick" method="post" path="/portals/{portalID}/gh/quickpicks" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.guidedhelp.createQuickpick({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    createQuickpick: {
      name: "QuickPick82700245",
      comment: "demo quickpick",
      casebaseReleaseId: "102312010000000",
      linkToActivity: false,
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGuidedhelpCreateQuickpick } from "@egain/egain-api-typescript/funcs/portalGuidedhelpCreateQuickpick.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpCreateQuickpick(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    language: "en-US",
    createQuickpick: {
      name: "QuickPick82700245",
      comment: "demo quickpick",
      casebaseReleaseId: "102312010000000",
      linkToActivity: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalGuidedhelpCreateQuickpick failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateQuickpickRequest](../../models/operations/createquickpickrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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

## getAllQuickPicks

## Overview
  The Get All Quickpicks for a Portal API retrieves details of quickpicks created for the Casebase.

## Conditions
   If "getLastSavedQuickPickForInteraction" query parameter is passed as "Yes" then one of below must be passed in request header.
   * X-ext-integration-id
   * X-egain-activity-id
   * X-ext-interaction-id
  Either casebaseID or getLastSavedQuickPickForInteraction must be passed in request.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAllQuickPicks" method="get" path="/portals/{portalID}/gh/quickpicks" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.getAllQuickPicks({
    acceptLanguage: "en-US",
    casebaseReleaseID: "202201000000002",
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
import { portalGuidedhelpGetAllQuickPicks } from "@egain/egain-api-typescript/funcs/portalGuidedhelpGetAllQuickPicks.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpGetAllQuickPicks(egain, {
    acceptLanguage: "en-US",
    casebaseReleaseID: "202201000000002",
    portalID: "PROD-1000",
    language: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpGetAllQuickPicks failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetAllQuickPicksRequest](../../models/operations/getallquickpicksrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.QuickpickResults](../../models/quickpickresults.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## restoreQuickpick

## Overview
  The Resume a Quickpick API can be used to restore (resume) a specific quickpick.

## Prerequisites
   * A Guided Help session for the Casebase must be started before invoking this API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="restoreQuickpick" method="post" path="/portals/{portalID}/gh/quickpicks/{quickpickID}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.guidedhelp.restoreQuickpick({
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    quickpickID: "11",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalGuidedhelpRestoreQuickpick } from "@egain/egain-api-typescript/funcs/portalGuidedhelpRestoreQuickpick.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalGuidedhelpRestoreQuickpick(egain, {
    acceptLanguage: "en-US",
    portalID: "PROD-1000",
    quickpickID: "11",
    language: "en-US",
    ghCustomAdditionalAttributes: "question.custom.score",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalGuidedhelpRestoreQuickpick failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RestoreQuickpickRequest](../../models/operations/restorequickpickrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.GHSearchResult](../../models/ghsearchresult.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |