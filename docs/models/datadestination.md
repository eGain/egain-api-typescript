# DataDestination

## Example Usage

```typescript
import { DataDestination } from "@egain/egain-api-typescript/models";

let value: DataDestination = {
  destinationType: "AWS S3 bucket",
  path: "s3://amzn-s3-demo-bucket/mydeptfolder",
  region: "us-west-2",
  credentials: {
    accessKey: "s3-access-key",
    secretKey: "s3-access-secret",
  },
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              | Example                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `destinationType`                                                        | [models.DestinationType](../models/destinationtype.md)                   | :heavy_check_mark:                                                       | Type of data destination                                                 | AWS S3 bucket                                                            |
| `path`                                                                   | *string*                                                                 | :heavy_check_mark:                                                       | Path of the data destination. For S3 bucket, it can be root or a folder. | s3://amzn-s3-demo-bucket/mydeptfolder                                    |
| `region`                                                                 | *string*                                                                 | :heavy_minus_sign:                                                       | Region of the data destination                                           | us-west-2                                                                |
| `credentials`                                                            | [models.Credentials](../models/credentials.md)                           | :heavy_minus_sign:                                                       | N/A                                                                      |                                                                          |