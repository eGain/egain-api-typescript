# DetailField

## Example Usage

```typescript
import { DetailField } from "@egain/egain-api-typescript/models";

let value: DetailField = {
  id: "PROD-9312",
};
```

## Fields

| Field                                                                                                         | Type                                                                                                          | Required                                                                                                      | Description                                                                                                   | Example                                                                                                       |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                          | *string*                                                                                                      | :heavy_minus_sign:                                                                                            | The ID of the Detail Field.<br>The ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-9312                                                                                                     |
| `detailLink`                                                                                                  | *string*                                                                                                      | :heavy_minus_sign:                                                                                            | link of the detail                                                                                            |                                                                                                               |
| `detailType`                                                                                                  | *string*                                                                                                      | :heavy_minus_sign:                                                                                            | type of the detail                                                                                            |                                                                                                               |
| `fieldName`                                                                                                   | *string*                                                                                                      | :heavy_minus_sign:                                                                                            | name of the field                                                                                             |                                                                                                               |