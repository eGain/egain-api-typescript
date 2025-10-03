# AnswerRange

## Example Usage

```typescript
import { AnswerRange } from "@egain/egain-api-typescript/models";

let value: AnswerRange = {
  id: "1000001035",
};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  | Example                                      |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `id`                                         | *string*                                     | :heavy_minus_sign:                           | Id of the answer range                       | 1000001035                                   |
| `min`                                        | *number*                                     | :heavy_minus_sign:                           | minimum value of range                       |                                              |
| `max`                                        | *number*                                     | :heavy_minus_sign:                           | maximum value of range                       |                                              |
| `minInclusive`                               | *boolean*                                    | :heavy_minus_sign:                           | flag indicating if minimum value is included |                                              |
| `maxInclusive`                               | *boolean*                                    | :heavy_minus_sign:                           | flag indicating if maximim value is included |                                              |