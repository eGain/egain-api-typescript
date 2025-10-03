# Personalization

Personalization allows the filtering of search results and controls the access to articles and article editions.

## Example Usage

```typescript
import { Personalization } from "@egain/egain-api-typescript/models";

let value: Personalization = {
  accessTags: {
    tagCategory: [
      {
        tags: {
          tag: [
            {
              name: "Blue",
              id: "PROD-13206",
            },
          ],
        },
        tagGroups: {
          tagGroup: [
            {
              id: "PROD-14566",
            },
          ],
        },
      },
    ],
  },
  filters: {
    tagCategory: [
      {
        tags: {
          tag: [
            {
              name: "Blue",
              id: "PROD-13206",
            },
          ],
        },
        tagGroups: {
          tagGroup: [
            {
              id: "PROD-14566",
            },
          ],
        },
      },
    ],
  },
  publishViews: {
    publishView: [
      {
        id: "PROD-12446",
        tagCategories: [
          {
            tagCategory: [
              {
                tags: {
                  tag: [
                    {
                      name: "Blue",
                      id: "PROD-13206",
                    },
                  ],
                },
                tagGroups: {
                  tagGroup: [
                    {
                      id: "PROD-14566",
                    },
                  ],
                },
              },
            ],
          },
        ],
      },
    ],
  },
};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `accessTags`                                                               | [models.PersonalizationAccessTags](../models/personalizationaccesstags.md) | :heavy_minus_sign:                                                         | N/A                                                                        |
| `filters`                                                                  | [models.Filters](../models/filters.md)                                     | :heavy_minus_sign:                                                         | N/A                                                                        |
| `publishViews`                                                             | [models.PublishViews](../models/publishviews.md)                           | :heavy_minus_sign:                                                         | N/A                                                                        |