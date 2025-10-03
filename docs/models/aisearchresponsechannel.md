# AISearchResponseChannel

## Example Usage

```typescript
import { AISearchResponseChannel } from "@egain/egain-api-typescript/models";

let value: AISearchResponseChannel = {
  type: "custom",
};
```

## Fields

| Field                                                                                               | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `type`                                                                                              | [models.AISearchResponseType](../models/aisearchresponsetype.md)                                    | :heavy_check_mark:                                                                                  | The channel where the query originated, e.g., directly from the portal or via a custom integration. |
| `name`                                                                                              | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The name of the channel.                                                                            |