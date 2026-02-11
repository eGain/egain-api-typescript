# AiservicesPrompt
(*aiservices.prompt*)

## Overview

### Available Operations

* [executePrompt](#executeprompt) - Execute a predefined prompt

## executePrompt

Execute a published and active prompt template from the AI console.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="executePrompt" method="post" path="/promptmanager/execute/prompt/{promptId}" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
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
import { aiservicesPromptExecutePrompt } from "@egain/egain-api-typescript/funcs/aiservicesPromptExecutePrompt.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await aiservicesPromptExecutePrompt(egain, {
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("aiservicesPromptExecutePrompt failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ExecutePromptRequest](../../models/operations/executepromptrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[models.ExecutePromptResponse](../../models/executepromptresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |