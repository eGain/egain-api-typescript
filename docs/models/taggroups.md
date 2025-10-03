# TagGroups

## Example Usage

```typescript
import { TagGroups } from "@egain/egain-api-typescript/models";

let value: TagGroups = {
  tagGroup: [
    {
      id: "PROD-14566",
    },
  ],
};
```

## Fields

| Field                                      | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `tagGroup`                                 | [models.TagGroup](../models/taggroup.md)[] | :heavy_minus_sign:                         | An array of tag groups.                    |