# TopicTreeResult

This schema contains the result of topic tree

## Example Usage

```typescript
import { TopicTreeResult } from "@egain/egain-api-typescript/models";

let value: TopicTreeResult = {
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

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `topicTree`                                          | [models.TopicTreeNode](../models/topictreenode.md)[] | :heavy_minus_sign:                                   | N/A                                                  |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |