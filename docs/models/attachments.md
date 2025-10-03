# Attachments

This schema contains the definition of Attachments.

## Example Usage

```typescript
import { Attachments } from "@egain/egain-api-typescript/models";

let value: Attachments = {
  attachments: [
    {
      id: "PROD-1001",
    },
  ],
};
```

## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `count`                                                            | *number*                                                           | :heavy_minus_sign:                                                 | The number of Attachments in the list.                             |
| `link`                                                             | [models.Link](../models/link.md)                                   | :heavy_minus_sign:                                                 | Defines the relationship between this resource and another object. |
| `attachments`                                                      | [models.AttachmentSummary](../models/attachmentsummary.md)[]       | :heavy_minus_sign:                                                 | The list of Attachments.                                           |