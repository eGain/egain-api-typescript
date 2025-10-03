# Comments

This schema contains the definition of an array of comments.

## Example Usage

```typescript
import { Comments } from "@egain/egain-api-typescript/models";

let value: Comments = {};
```

## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `count`                                  | *number*                                 | :heavy_minus_sign:                       | The number of comments.                  |
| `comments`                               | [models.Comment](../models/comment.md)[] | :heavy_minus_sign:                       | The list of comments.                    |