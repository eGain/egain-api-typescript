# AnswersRequestChannel

## Example Usage

```typescript
import { AnswersRequestChannel } from "@egain/egain-api-typescript/models";

let value: AnswersRequestChannel = {
  name: "Eight Bank Website",
};
```

## Fields

| Field                                                                                               | Type                                                                                                | Required                                                                                            | Description                                                                                         | Example                                                                                             |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `type`                                                                                              | [models.AnswersRequestType](../models/answersrequesttype.md)                                        | :heavy_minus_sign:                                                                                  | The channel where the query originated, e.g., directly from the portal or via a custom integration. | custom                                                                                              |
| `name`                                                                                              | *string*                                                                                            | :heavy_minus_sign:                                                                                  | A descriptive name for the channel (e.g., "web", "mobile app", "agent console").                    | Eight Bank Website                                                                                  |