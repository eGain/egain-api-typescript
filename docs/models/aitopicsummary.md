# AITopicSummary

This schema contains the topic ID and name of the topics. This is used by TopicBreadcrumb.

## Example Usage

```typescript
import { AITopicSummary } from "@egain/egain-api-typescript/models";

let value: AITopicSummary = {
  id: "PROD-1921",
  name: "Banking Regulations",
};
```

## Fields

| Field                                                                                                                       | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 | Example                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                        | *string*                                                                                                                    | :heavy_minus_sign:                                                                                                          | The alphanumeric ID of the topic.<br><br>A topic ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1921                                                                                                                   |
| `name`                                                                                                                      | *string*                                                                                                                    | :heavy_minus_sign:                                                                                                          | The name of the topic.                                                                                                      | Banking Regulations                                                                                                         |