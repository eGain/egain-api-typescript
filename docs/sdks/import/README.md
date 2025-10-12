# Import
(*content.import*)

## Overview

### Available Operations

* [createImportJob](#createimportjob) - Import content from external sources by creating an import job
* [getImportStatus](#getimportstatus) - Get the current status of an import or validation job
* [createImportValidationJob](#createimportvalidationjob) - Validate content structure and format before import by creating an import validation job
* [cancelImport](#cancelimport) - Cancel an import or validation job

## createImportJob

# Import Content

## Overview
This API initiates a bulk content import operation from Data Sources. It creates an asynchronous import job that processes content in the background, allowing you to import large volumes of content without blocking your application.

## Pre-requisties
1. Content in Data Source needs to be in this format: [Guide to Data Import Format](https://apidev.egain.com/developer-portal/guides/ingestion/data-import-format-guide/)

## How It Works
1. **Job Creation**: The API creates an import job and returns a unique job ID
2. **Content Processing**: Content is processed asynchronously in the background
3. **Status Monitoring**: Use the job ID to monitor progress via the Status API
4. **Completion**: Job completes when all content is processed or errors occur

## Supported Operations
- **Import**: Add new content to the knowledge base
- **Update**: Modify existing content

## Data Source Types
- AWS S3 bucket
- Shared file path

## Best Practices
- **Scheduling**: Use scheduleTime for off-peak imports to minimize system impact
- **Monitoring**: Regularly check job status and logs for any issues
- **Error Handling**: Review failed items and retry with corrections

## Permissions
| Actor | Permission |
| ------- | --------|
| User |<ul><li>User must be a department user.</li><li>Content can only be imported in user's home department.</li><li>User must have 'Author' role.</li><li>Content can only be imported if the user has all the required languages assigned.</li></ul>|


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createImportJob" method="post" path="/import/content" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.content.import.createImportJob({
    dataSource: {
      type: "AWS S3 bucket",
      path: "s3://mybucket/myfolder/",
      region: "us-east-1",
      credentials: {},
    },
    operation: "import",
    scheduleTime: {
      date: new Date("2024-03-01T10:00:00.000Z"),
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
import { contentImportCreateImportJob } from "@egain/egain-api-typescript/funcs/contentImportCreateImportJob.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await contentImportCreateImportJob(egain, {
    dataSource: {
      type: "AWS S3 bucket",
      path: "s3://mybucket/myfolder/",
      region: "us-east-1",
      credentials: {},
    },
    operation: "import",
    scheduleTime: {
      date: new Date("2024-03-01T10:00:00.000Z"),
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("contentImportCreateImportJob failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ImportContent](../../models/importcontent.md)                                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.CreateImportJobResponse](../../models/operations/createimportjobresponse.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.WSErrorCommon        | 400, 401, 403, 406          | application/json            |
| errors.SchemasWSErrorCommon | 412                         | application/json            |
| errors.WSErrorCommon        | 500                         | application/json            |
| errors.EgainDefaultError    | 4XX, 5XX                    | \*/\*                       |

## getImportStatus

# Get Import Job Status

## Overview
This API provides real-time status information for content import and validation operations. Use this endpoint to monitor job progress, check completion status, and access detailed logs and error information.

## Status Values
- **Scheduled**: Job is queued and waiting for scheduled execution time
- **In Progress**: Job is actively processing content
- **Completed**: Job finished successfully
- **Failed**: Job encountered errors and could not complete
- **Cancelled**: Job was manually cancelled by user

## Response Information
- **Current Status**: Real-time job status
- **Progress Metrics**: Items processed, total items, completion percentage
- **Log Files**: Location of detailed operation logs
- **Error Details**: Specific errors encountered during processing
- **Timing Information**: Start time, estimated completion, actual completion

## Log File Access
Log files contain detailed information about:
- Content processing steps
- Validation results
- Error details with context


## Permissions
| Actor | Permission |
| ------- | --------|
| User |<ul><li>User must be a department user.</li><li>User must have 'Author' role.</li><li>The job must have been created by the logged in user, or the logged in user must have 'View' permissions on the user who created the job.</li></ul>|


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getImportStatus" method="get" path="/import/content/{job_id}/status" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.content.import.getImportStatus({
    jobId: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { contentImportGetImportStatus } from "@egain/egain-api-typescript/funcs/contentImportGetImportStatus.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await contentImportGetImportStatus(egain, {
    jobId: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("contentImportGetImportStatus failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetImportStatusRequest](../../models/operations/getimportstatusrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[models.ImportStatus](../../models/importstatus.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## createImportValidationJob

# Validate Import Content

## Overview
This API enables users to validate content structure, format, and compliance before importing it into the production knowledge base. Validation is a non-destructive operation that checks content without making any changes to your existing data.

## What Validation Checks
- **Content Structure**: Verifies required fields and data types
- **Format Compliance**: Ensures content meets platform requirements
- **Language Support**: Validates content against supported languages
- **Metadata Mapping**: Checks field mappings and transformations
- **Business Rules**: Validates against department-specific rules

## Validation Benefits
- **Risk Mitigation**: Identify issues before affecting production data
- **Quality Assurance**: Ensure content meets organizational standards
- **Cost Savings**: Avoid failed imports that waste processing time
- **Compliance**: Meet regulatory and internal content requirements

## Validation Process
1. **Content Analysis**: System analyzes content structure and format
2. **Rule Validation**: Applies business rules and validation logic
3. **Quality Assessment**: Evaluates content quality and completeness
4. **Report Generation**: Creates detailed validation report
5. **Issue Categorization**: Classifies issues by severity and type

## Common Validation Issues
- **Missing Required Fields**: Title, description, category, etc.
- **Invalid Data Types**: Incorrect field formats (dates, numbers, etc.)
- **Language Mismatches**: Content language not supported by department

## Best Practices
- **Always Validate First**: Run validation before any import operation
- **Review Reports**: Carefully examine validation results and warnings
- **Fix Issues**: Address validation errors before proceeding with import
- **Test Small Batches**: Validate with small content samples first
- **Iterate**: Use validation feedback to improve content quality

## Permissions 
| Actor | Permission |
| ------- | --------|
| User |<ul><li>User must be a department user.</li><li>User must have 'Author' role.</li><li>Content can only be imported if the user has all the required languages assigned.</li></ul>|


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createImportValidationJob" method="post" path="/import/content/validate" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.content.import.createImportValidationJob({
    dataSource: {
      type: "AWS S3 bucket",
      path: "s3://mybucket/myfolder/",
      region: "us-east-1",
      credentials: {},
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
import { contentImportCreateImportValidationJob } from "@egain/egain-api-typescript/funcs/contentImportCreateImportValidationJob.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await contentImportCreateImportValidationJob(egain, {
    dataSource: {
      type: "AWS S3 bucket",
      path: "s3://mybucket/myfolder/",
      region: "us-east-1",
      credentials: {},
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("contentImportCreateImportValidationJob failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ValidateImportContent](../../models/validateimportcontent.md)                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.CreateImportValidationJobResponse](../../models/operations/createimportvalidationjobresponse.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.WSErrorCommon        | 400, 401, 403, 406          | application/json            |
| errors.SchemasWSErrorCommon | 412                         | application/json            |
| errors.WSErrorCommon        | 500                         | application/json            |
| errors.EgainDefaultError    | 4XX, 5XX                    | \*/\*                       |

## cancelImport

# Cancel Import or Validation Job

## Overview
This API allows users to cancel import or validation operations that are currently in progress or scheduled for future execution. Cancellation is immediate for scheduled jobs and graceful for running jobs.

## Cancellation Behavior
- **Scheduled Jobs**: Immediate cancellation, no processing occurs
- **In Progress Jobs**: Graceful shutdown, current item completes, no new items start
- **Completed Jobs**: Cannot be cancelled (returns error)
- **Failed Jobs**: Cannot be cancelled (already stopped)

## When to Cancel
- **Content Issues**: Discover problems with source content
- **Timing Changes**: Need to reschedule for different time
- **Resource Constraints**: System resources are needed elsewhere
- **User Request**: Manual cancellation by authorized users
- **System Maintenance**: Planned maintenance windows

## Cancellation Process
1. **Request Received**: System receives cancellation request
2. **Status Check**: Verifies current job status
3. **Graceful Shutdown**: For running jobs, completes current item
4. **Resource Cleanup**: Releases allocated system resources
5. **Status Update**: Marks job as cancelled
6. **Notification**: Updates job status and logs

## Post-Cancellation
- **Job Status**: Changes to "Cancelled"
- **Partial Results**: Any completed items remain in system
- **Logs**: Cancellation reason and timing recorded
- **Resources**: System resources freed for other operations

## Best Practices
- **Monitor Jobs**: Regularly check job status to identify candidates for cancellation
- **Plan Cancellations**: Schedule cancellations during low-usage periods
- **Resource Planning**: Consider resource impact before cancelling large jobs

## Permissions 
| Actor | Permission |
| ------- | --------|
| User |<li>User must be a department user.</li><li>Content can only be validated for user's home department.</li><li>User must have 'Author' role.</li><li>The job must have been created by the logged in user, or the logged in user must have 'Edit' permissions on the user who created the job.</li></ul>|


### Example Usage

<!-- UsageSnippet language="typescript" operationID="cancelImport" method="post" path="/import/content/{job_id}/cancel" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.content.import.cancelImport({
    jobId: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { contentImportCancelImport } from "@egain/egain-api-typescript/funcs/contentImportCancelImport.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await contentImportCancelImport(egain, {
    jobId: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("contentImportCancelImport failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CancelImportRequest](../../models/operations/cancelimportrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 401, 403, 404, 406       | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |