# TopicResult

A TopicResult defines a response from any of the Topic APIs.

## Example Usage

```typescript
import { TopicResult } from "@egain/egain-api-typescript/models";

let value: TopicResult = {
  topic: [
    {
      id: "<id>",
      name: "<value>",
      departmentId: "1000001035",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `topic`                                              | [models.Topic](../models/topic.md)[]                 | :heavy_minus_sign:                                   | N/A                                                  |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |