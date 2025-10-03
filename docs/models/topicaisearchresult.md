# TopicAISearchResult

This schema contains general information about the topic.

## Example Usage

```typescript
import { TopicAISearchResult } from "@egain/egain-api-typescript/models";

let value: TopicAISearchResult = {
  name: "<value>",
  id: "<id>",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `name`                                                                                        | *string*                                                                                      | :heavy_check_mark:                                                                            | Name of Topic.                                                                                |
| `articleCountInTopic`                                                                         | *number*                                                                                      | :heavy_minus_sign:                                                                            | Number of articles within the topic.                                                          |
| `articleCountInTopicTree`                                                                     | *number*                                                                                      | :heavy_minus_sign:                                                                            | Number of articles in this topic and all sub-topics.                                          |
| `createdBy`                                                                                   | *number*                                                                                      | :heavy_minus_sign:                                                                            | The ID of the user that created this resource.                                                |
| `createdDate`                                                                                 | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `departmentId`                                                                                | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `lastModifiedBy`                                                                              | *number*                                                                                      | :heavy_minus_sign:                                                                            | The ID of the user that modified this resource.                                               |
| `lastModifiedDate`                                                                            | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `id`                                                                                          | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `childCount`                                                                                  | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |