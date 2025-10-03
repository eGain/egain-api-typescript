# TopicBreadcrumb

This schema contains one or more TopicSummary instances.

## Example Usage

```typescript
import { TopicBreadcrumb } from "@egain/egain-api-typescript/models";

let value: TopicBreadcrumb = {
  topicSummary: [
    {
      id: "PROD-1921",
    },
  ],
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `topicSummary`                                     | [models.TopicSummary](../models/topicsummary.md)[] | :heavy_minus_sign:                                 | An instance of TopicSummary.                       |