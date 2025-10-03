# DisplayField

## Example Usage

```typescript
import { DisplayField } from "@egain/egain-api-typescript/models";

let value: DisplayField = {
  id: "PROD-9312",
};
```

## Fields

| Field                                                                                                          | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    | Example                                                                                                        |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                           | *string*                                                                                                       | :heavy_minus_sign:                                                                                             | The ID of the Display Field.<br>The ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-9312                                                                                                      |
| `content`                                                                                                      | *string*                                                                                                       | :heavy_minus_sign:                                                                                             | content in bytes. 2 MB max                                                                                     |                                                                                                                |
| `fieldName`                                                                                                    | *any*                                                                                                          | :heavy_minus_sign:                                                                                             | name of the field                                                                                              |                                                                                                                |