# Export
(*portal.export*)

## Overview

### Available Operations

* [exportContent](#exportcontent) - Export Knowledge
* [exportStatus](#exportstatus) - Get Export Job Status

## exportContent

## Overview
   The Content Export API initiates a bulk export of the Knowledge Hub to a client-provided Amazon S3 bucket or SFTP server path.
   It returns a URL with a Job ID to enable tracking the status of this asynchronous operation.  
   Each export job can send multiple JSON files, depending on the total number of items to process. 
   More than one bulk export can take place, as needed, one per portal.

## Permission
  * Only a client application can invoke this API.   


### Example Usage

<!-- UsageSnippet language="typescript" operationID="exportContent" method="post" path="/content/export" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.export.exportContent({
    portalID: "PROD-1000",
    language: {
      code: "en-US",
    },
    resourceTypes: [
      "articles",
    ],
    dataDestination: {
      destinationType: "AWS S3 bucket",
      path: "https://s3.us-west-2.amazonaws.com/amzn-s3-demo-bucket1",
      region: "us-west-2",
      credentials: {
        accessKey: "s3-access-user",
        secretKey: "s3-access-secret",
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
import { portalExportExportContent } from "@egain/egain-api-typescript/funcs/portalExportExportContent.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalExportExportContent(egain, {
    portalID: "PROD-1000",
    language: {
      code: "en-US",
    },
    resourceTypes: [
      "articles",
    ],
    dataDestination: {
      destinationType: "AWS S3 bucket",
      path: "https://s3.us-west-2.amazonaws.com/amzn-s3-demo-bucket1",
      region: "us-west-2",
      credentials: {
        accessKey: "s3-access-user",
        secretKey: "s3-access-secret",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalExportExportContent failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.KnowledgeExport](../../models/knowledgeexport.md)                                                                                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ExportContentResponse](../../models/operations/exportcontentresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401                 | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## exportStatus

## Overview
   The Content Export Status API provides real-time status information to monitor job progress and check completion status.

## Status Values
- **Pending**: Job is pending start of processing
- **In Progress**: Job is actively processing content        
- **Completed**: Job finished successfully
- **Failed**: Job encountered errors and could not complete

## Response Information
- **Current Status**: Real-time job status
- **Progress Metrics**: Items processed, total items
- **Error Details**: Specific errors encountered during processing
- **Timing Information**: Start time, estimated completion, actual completion           

## Permission
  * Only a client application can invoke this API.  


### Example Usage

<!-- UsageSnippet language="typescript" operationID="exportStatus" method="get" path="/content/export/{jobID}/status" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.export.exportStatus({
    jobID: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalExportExportStatus } from "@egain/egain-api-typescript/funcs/portalExportExportStatus.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalExportExportStatus(egain, {
    jobID: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalExportExportStatus failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ExportStatusRequest](../../models/operations/exportstatusrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ExportStatus](../../models/exportstatus.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |