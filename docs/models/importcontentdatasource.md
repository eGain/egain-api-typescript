# ImportContentDataSource

## Example Usage

```typescript
import { ImportContentDataSource } from "@egain/egain-api-typescript/models";

let value: ImportContentDataSource = {
  type: "AWS S3 bucket",
  path: "https://thorough-handful.org",
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `type`                                                                   | [models.ImportContentType](../models/importcontenttype.md)               | :heavy_check_mark:                                                       | Type of data source                                                      |
| `path`                                                                   | *string*                                                                 | :heavy_check_mark:                                                       | Path of the data source                                                  |
| `region`                                                                 | *string*                                                                 | :heavy_minus_sign:                                                       | Region of the data source                                                |
| `credentials`                                                            | [models.ImportContentCredentials](../models/importcontentcredentials.md) | :heavy_minus_sign:                                                       | N/A                                                                      |