# AnswersResponseChannel

## Example Usage

```typescript
import { AnswersResponseChannel } from "@egain/egain-api-typescript/models";

let value: AnswersResponseChannel = {
  type: "custom",
  name: "Eight Bank Website",
};
```

## Fields

| Field                                                                                               | Type                                                                                                | Required                                                                                            | Description                                                                                         | Example                                                                                             |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `type`                                                                                              | [models.AnswersResponseType](../models/answersresponsetype.md)                                      | :heavy_check_mark:                                                                                  | The channel where the query originated, e.g., directly from the portal or via a custom integration. | custom                                                                                              |
| `name`                                                                                              | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The channel name.                                                                                   | Eight Bank Website                                                                                  |