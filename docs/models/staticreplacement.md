# StaticReplacement

## Example Usage

```typescript
import { StaticReplacement } from "@egain/egain-api-typescript/models";

let value: StaticReplacement = {
  type: "static",
  name: "<value>",
  value: "<value>",
};
```

## Fields

| Field                                                                                                                                           | Type                                                                                                                                            | Required                                                                                                                                        | Description                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`                                                                                                                                          | [models.StaticReplacementType](../models/staticreplacementtype.md)                                                                              | :heavy_check_mark:                                                                                                                              | Identifies this replacement as a **static value**. At execution, the specified `value` will replace the variable `name` in the prompt template. |
| `name`                                                                                                                                          | *string*                                                                                                                                        | :heavy_check_mark:                                                                                                                              | The placeholder variable in the prompt template that will be replaced.                                                                          |
| `value`                                                                                                                                         | *string*                                                                                                                                        | :heavy_check_mark:                                                                                                                              | The literal value to insert into the prompt when executed.                                                                                      |