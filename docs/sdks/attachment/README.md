# Attachment
(*portal.attachment*)

## Overview

### Available Operations

* [createSignedURL](#createsignedurl) - Generate Signed URL to Upload API
* [uploadAttachment](#uploadattachment) - Upload Attachment

## createSignedURL

## Overview
   The Generate Signed URL to Upload API produces a signature that is used to upload an attachment. 


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createSignedURL" method="post" path="/attachment/preupload" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.portal.attachment.createSignedURL({
    acceptLanguage: "en-US",
    attachmentUpload: {
      name: "article.png",
      size: 11889,
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
import { portalAttachmentCreateSignedURL } from "@egain/egain-api-typescript/funcs/portalAttachmentCreateSignedURL.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalAttachmentCreateSignedURL(egain, {
    acceptLanguage: "en-US",
    attachmentUpload: {
      name: "article.png",
      size: 11889,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("portalAttachmentCreateSignedURL failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateSignedURLRequest](../../models/operations/createsignedurlrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Attachment](../../models/attachment.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.WSErrorCommon     | 400, 401, 403, 404, 406  | application/json         |
| errors.WSErrorCommon     | 500                      | application/json         |
| errors.EgainDefaultError | 4XX, 5XX                 | \*/\*                    |

## uploadAttachment

## Overview
   The Upload Attachment API uses the signed URL produced by the Generate Signed URL to Upload API to upload an attachment. 
   The Make a Suggestion API uses this API to upload attachments.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="uploadAttachment" method="post" path="/attachment/upload" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";
import { openAsBlob } from "node:fs";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  await egain.portal.attachment.uploadAttachment({
    acceptLanguage: "en-US",
    signature: "<value>",
    requestBody: await openAsBlob("example.file"),
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { portalAttachmentUploadAttachment } from "@egain/egain-api-typescript/funcs/portalAttachmentUploadAttachment.js";
import { openAsBlob } from "node:fs";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const res = await portalAttachmentUploadAttachment(egain, {
    acceptLanguage: "en-US",
    signature: "<value>",
    requestBody: await openAsBlob("example.file"),
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("portalAttachmentUploadAttachment failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UploadAttachmentRequest](../../models/operations/uploadattachmentrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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