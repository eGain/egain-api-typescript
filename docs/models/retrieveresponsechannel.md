# RetrieveResponseChannel

## Example Usage

```typescript
import { RetrieveResponseChannel } from "@egain/egain-api-typescript/models";

let value: RetrieveResponseChannel = {
  type: "custom",
  name: "Eight Bank Page",
};
```

## Fields

| Field                                                                                               | Type                                                                                                | Required                                                                                            | Description                                                                                         | Example                                                                                             |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `type`                                                                                              | [models.RetrieveResponseType](../models/retrieveresponsetype.md)                                    | :heavy_check_mark:                                                                                  | The channel where the query originated, e.g., directly from the portal or via a custom integration. | custom                                                                                              |
| `name`                                                                                              | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The channel name.                                                                                   | Eight Bank Page                                                                                     |