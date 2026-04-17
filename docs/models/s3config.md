# S3Config

## Example Usage

```typescript
import { S3Config } from "@egain/egain-api-typescript/models";

let value: S3Config = {
  region: "us-west-2",
  accessKey: "s3-access-key",
  secretKey: "s3-access-secret",
};
```

## Fields

| Field                          | Type                           | Required                       | Description                    | Example                        |
| ------------------------------ | ------------------------------ | ------------------------------ | ------------------------------ | ------------------------------ |
| `region`                       | *string*                       | :heavy_check_mark:             | Region of the data destination | us-west-2                      |
| `accessKey`                    | *string*                       | :heavy_check_mark:             | N/A                            | s3-access-key                  |
| `secretKey`                    | *string*                       | :heavy_check_mark:             | N/A                            | s3-access-secret               |