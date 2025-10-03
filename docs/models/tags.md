# Tags

## Example Usage

```typescript
import { Tags } from "@egain/egain-api-typescript/models";

let value: Tags = {
  tag: [
    {
      name: "Blue",
      id: "PROD-13206",
    },
  ],
};
```

## Fields

| Field                            | Type                             | Required                         | Description                      |
| -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| `tag`                            | [models.Tag](../models/tag.md)[] | :heavy_minus_sign:               | An array of tags.                |