# AITopicBreadcrumb

This schema contains one or more TopicSummary instances.

## Example Usage

```typescript
import { AITopicBreadcrumb } from "@egain/egain-api-typescript/models";

let value: AITopicBreadcrumb = {
  topicSummary: [
    {
      id: "PROD-1921",
      name: "Banking Regulations",
    },
  ],
};
```

## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `topicSummary`                                         | [models.AITopicSummary](../models/aitopicsummary.md)[] | :heavy_minus_sign:                                     | An instance of TopicSummary.                           |