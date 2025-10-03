# SchemasAnswer

## Example Usage

```typescript
import { SchemasAnswer } from "@egain/egain-api-typescript/models";

let value: SchemasAnswer = {
  id: "1000001035",
};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  | Example                                      |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `id`                                         | *string*                                     | :heavy_minus_sign:                           | ID of the answer                             | 1000001035                                   |
| `depth`                                      | *number*                                     | :heavy_minus_sign:                           | depth of the answer                          |                                              |
| `isInvisible`                                | *boolean*                                    | :heavy_minus_sign:                           | Flag indicating if answer is visible         |                                              |
| `text`                                       | *string*                                     | :heavy_minus_sign:                           | Text of the answer                           |                                              |
| `image`                                      | [models.Image](../models/image.md)           | :heavy_minus_sign:                           | N/A                                          |                                              |
| `conceptName`                                | *string*                                     | :heavy_minus_sign:                           | name of the answer                           |                                              |
| `conceptId`                                  | *string*                                     | :heavy_minus_sign:                           | Id of the answer                             |                                              |
| `lowerValue`                                 | *number*                                     | :heavy_minus_sign:                           | lower value of the answer                    |                                              |
| `upperValue`                                 | *number*                                     | :heavy_minus_sign:                           | upper value of the answer                    |                                              |
| `enumLowerValue`                             | *string*                                     | :heavy_minus_sign:                           | lower value of enum answer                   |                                              |
| `enumUpperValue`                             | *string*                                     | :heavy_minus_sign:                           | upper value of enum answer                   |                                              |
| `lowerInclusive`                             | *boolean*                                    | :heavy_minus_sign:                           | Value indicating if lower value is inclusive |                                              |
| `upperInclusive`                             | *boolean*                                    | :heavy_minus_sign:                           | Value indicating if upper value is inclusive |                                              |
| `partialMin`                                 | *number*                                     | :heavy_minus_sign:                           | Partial minimum                              |                                              |
| `partialMax`                                 | *number*                                     | :heavy_minus_sign:                           | Partial maximim                              |                                              |