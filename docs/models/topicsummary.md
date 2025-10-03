# TopicSummary

This schema contains the topic ID and name of the topics. This is used by TopicBreadcrumb.

## Example Usage

```typescript
import { TopicSummary } from "@egain/egain-api-typescript/models";

let value: TopicSummary = {
  id: "PROD-1921",
};
```

## Fields

| Field                                                                                                                       | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 | Example                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                        | *string*                                                                                                                    | :heavy_minus_sign:                                                                                                          | The alphanumeric ID of the topic.<br><br>A topic ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1921                                                                                                                   |
| `name`                                                                                                                      | *string*                                                                                                                    | :heavy_minus_sign:                                                                                                          | The name of the topic.                                                                                                      |                                                                                                                             |
| `link`                                                                                                                      | [models.Link](../models/link.md)                                                                                            | :heavy_minus_sign:                                                                                                          | Defines the relationship between this resource and another object.                                                          |                                                                                                                             |