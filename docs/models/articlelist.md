# ArticleList

Success

## Example Usage

```typescript
import { ArticleList } from "@egain/egain-api-typescript/models";

let value: ArticleList = {
  name: "<value>",
  id: "<id>",
  typeId: "12",
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

| Field                                                                                                                                                    | Type                                                                                                                                                     | Required                                                                                                                                                 | Description                                                                                                                                              | Example                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`                                                                                                                                                   | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | The name of the article list.                                                                                                                            |                                                                                                                                                          |
| `id`                                                                                                                                                     | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | The ID of the article list.<br><br>An article list ID is either a 4-digit number or composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |                                                                                                                                                          |
| `description`                                                                                                                                            | *string*                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The description of the article list. The maximum allowed article list description size is 1 KB.                                                          |                                                                                                                                                          |
| `typeId`                                                                                                                                                 | *string*                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The type of the article list.                                                                                                                            | 12                                                                                                                                                       |
| `articles`                                                                                                                                               | [models.ArticleResult](../models/articleresult.md)[]                                                                                                     | :heavy_minus_sign:                                                                                                                                       | An array of articles that belong to the article list.                                                                                                    |                                                                                                                                                          |
| `link`                                                                                                                                                   | [models.Link](../models/link.md)                                                                                                                         | :heavy_minus_sign:                                                                                                                                       | Defines the relationship between this resource and another object.                                                                                       |                                                                                                                                                          |