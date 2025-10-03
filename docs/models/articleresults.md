# ArticleResults

One or more instances of an Article result.

## Example Usage

```typescript
import { ArticleResults } from "@egain/egain-api-typescript/models";

let value: ArticleResults = {
  articles: [
    {
      articleType: {
        articleTypeId: "932100000002020",
      },
      topicBreadcrumb: [
        {
          topicSummary: [
            {
              id: "PROD-1921",
            },
          ],
        },
      ],
      personalization: {
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
      },
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `articles`                                           | [models.ArticleResult](../models/articleresult.md)[] | :heavy_minus_sign:                                   | Article details<br/>                                 |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |