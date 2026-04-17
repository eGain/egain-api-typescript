# TopicBreadcrumbsList

This schema contains an array of topic breadcrumbs, allowing clients to distinguish between multiple distinct hierarchical topic paths.

## Example Usage

```typescript
import { TopicBreadcrumbsList } from "@egain/egain-api-typescript/models";

let value: TopicBreadcrumbsList = {
  topicBreadcrumb: [
    {
      topicSummary: [
        {
          id: "PROD-1921",
        },
      ],
    },
  ],
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `topicBreadcrumb`                                                    | [models.TopicBreadcrumb](../models/topicbreadcrumb.md)[]             | :heavy_minus_sign:                                                   | An array of TopicBreadcrumb instances representing individual paths. |