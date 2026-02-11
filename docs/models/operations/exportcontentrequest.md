# ExportContentRequest

## Example Usage

```typescript
import { ExportContentRequest } from "@egain/egain-api-typescript/models/operations";

let value: ExportContentRequest = {
  acceptLanguage: "en-US",
  knowledgeExport: {
    portalID: "PROD-1000",
    language: {
      code: "en-US",
    },
    resourceTypes: [
      "articles",
    ],
    dataDestination: {
      destinationType: "AWS S3 bucket",
      path: "s3://amzn-s3-demo-bucket/mydeptfolder",
      region: "us-west-2",
      credentials: {
        accessKey: "s3-access-key",
        secretKey: "s3-access-secret",
      },
    },
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `knowledgeExport`                                                                                                               | [models.KnowledgeExport](../../models/knowledgeexport.md)                                                                       | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             |                                                                                                                                 |