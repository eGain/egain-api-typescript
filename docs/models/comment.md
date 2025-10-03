# Comment

This schema contains the definition of a comment object.

## Example Usage

```typescript
import { Comment } from "@egain/egain-api-typescript/models";

let value: Comment = {};
```

## Fields

| Field                                      | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `id`                                       | *string*                                   | :heavy_minus_sign:                         | The ID of the comment.                     |
| `content`                                  | *string*                                   | :heavy_minus_sign:                         | The content of the comment.                |
| `createdBy`                                | [models.CreatedBy](../models/createdby.md) | :heavy_minus_sign:                         | N/A                                        |
| `createdDate`                              | *string*                                   | :heavy_minus_sign:                         | N/A                                        |