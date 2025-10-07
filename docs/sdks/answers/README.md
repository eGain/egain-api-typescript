# Answers
(*aiservices.answers*)

## Overview

### Available Operations

* [getBestAnswer](#getbestanswer) - Get the best answer for a user query

## getBestAnswer

The **Answers API** allows enterprises to deliver fast, accurate, and contextual responses powered by their organizational knowledge. It supports two complementary approaches:  
<li> **Certified Answers**: Direct snippets retrieved from enterprise-authored content. </li>  
<li> **Generative Answers**: Natural language responses synthesized by a large language model (LLM).  </li>

Every response includes supporting search results, references, and confidence scores—ensuring transparency, trust, and traceability. The API is built for secure, scalable integration across enterprise environments.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getBestAnswer" method="post" path="/{portalID}/answers" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.answers.getBestAnswer({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
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
import { aiservicesAnswersGetBestAnswer } from "@egain/egain-api-typescript/funcs/aiservicesAnswersGetBestAnswer.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await aiservicesAnswersGetBestAnswer(egain, {
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("aiservicesAnswersGetBestAnswer failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetBestAnswerRequest](../../models/operations/getbestanswerrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[models.AnswersResponse](../../models/answersresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |