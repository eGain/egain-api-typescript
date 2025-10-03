# Usermilestones
(*portal.usermilestones*)

## Overview

### Available Operations

* [getUserMilestones](#getusermilestones) - Get User Milestones

## getUserMilestones

## Overview
The User Milestones API provides information about the milestones of an agent within the article workflow. 
This API helps track the progress of articles by grouping them into relevant milestones based on their current stage.

For example, an article might go through Knowledge Workflow Stages like Draft, Initial Review, Staging, Final Review and Publish. 
       Articles in the Draft and Initial Review stages are part of the "authoring milestone", while articles in the Staging and Final Review stages are part of the "staging milestone".


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getUserMilestones" method="get" path="/portals/user/milestones" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.portal.usermilestones.getUserMilestones({
    acceptLanguage: "en-US",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalUsermilestonesGetUserMilestones } from "@egain/egain-api-typescript/funcs/portalUsermilestonesGetUserMilestones.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await portalUsermilestonesGetUserMilestones(egain, {
    acceptLanguage: "en-US",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalUsermilestonesGetUserMilestones failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetUserMilestonesRequest](../../models/operations/getusermilestonesrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Milestones](../../models/milestones.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |