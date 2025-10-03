# TopicTreeNode

This schema contains general information about the TopicTree.

## Example Usage

```typescript
import { TopicTreeNode } from "@egain/egain-api-typescript/models";

let value: TopicTreeNode = {
  topic: {
    id: "<id>",
    name: "<value>",
    departmentId: "1000001035",
  },
  topicTree: [
    {
      topic: {
        id: "<id>",
        name: "<value>",
        departmentId: "1000001035",
      },
    },
  ],
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `topic`                                                   | [models.Topic](../models/topic.md)                        | :heavy_minus_sign:                                        | This schema contains general information about the topic. |
| `topicTree`                                               | [models.TopicTreeNode](../models/topictreenode.md)[]      | :heavy_minus_sign:                                        | N/A                                                       |