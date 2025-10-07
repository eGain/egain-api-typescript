# DataDestination

## Example Usage

```typescript
import { DataDestination } from "@egain/egain-api-typescript/models";

let value: DataDestination = {
  destinationType: "AWS S3 bucket",
  path: "s3://amzn-s3-demo-bucket/mydeptfolder",
  region: "us-west-2",
  credentials: {
    accessKey: "s3-access-user",
    secretKey: "s3-access-secret",
  },
};
```

## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  | Example                                                                      |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `destinationType`                                                            | [models.DestinationType](../models/destinationtype.md)                       | :heavy_check_mark:                                                           | Type of data destination                                                     | AWS S3 bucket                                                                |
| `path`                                                                       | *string*                                                                     | :heavy_check_mark:                                                           | Path of the data destination                                                 | s3://amzn-s3-demo-bucket/mydeptfolder                                        |
| `region`                                                                     | *string*                                                                     | :heavy_minus_sign:                                                           | Region of the data destination                                               | us-west-2                                                                    |
| `credentials`                                                                | [models.KnowledgeExportCredentials](../models/knowledgeexportcredentials.md) | :heavy_minus_sign:                                                           | N/A                                                                          |                                                                              |