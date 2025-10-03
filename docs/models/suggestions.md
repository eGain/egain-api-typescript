# Suggestions

One or more instances of Suggestion.

## Example Usage

```typescript
import { Suggestions } from "@egain/egain-api-typescript/models";

let value: Suggestions = {
  suggestion: [
    {
      id: "PROD-0623",
      name: "<value>",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `suggestion`                                         | [models.Suggestion](../models/suggestion.md)[]       | :heavy_minus_sign:                                   | N/A                                                  |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |