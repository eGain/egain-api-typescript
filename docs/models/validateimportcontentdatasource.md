# ValidateImportContentDataSource

## Example Usage

```typescript
import { ValidateImportContentDataSource } from "@egain/egain-api-typescript/models";

let value: ValidateImportContentDataSource = {
  type: "Shared file path",
  path: "https://hidden-adviser.name",
};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `type`                                                                                   | [models.ValidateImportContentType](../models/validateimportcontenttype.md)               | :heavy_check_mark:                                                                       | Type of data source                                                                      |
| `path`                                                                                   | *string*                                                                                 | :heavy_check_mark:                                                                       | Path of the data source                                                                  |
| `region`                                                                                 | *string*                                                                                 | :heavy_minus_sign:                                                                       | Region of the data source                                                                |
| `credentials`                                                                            | [models.ValidateImportContentCredentials](../models/validateimportcontentcredentials.md) | :heavy_minus_sign:                                                                       | N/A                                                                                      |