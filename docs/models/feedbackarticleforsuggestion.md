# FeedbackArticleForSuggestion

This schema contains information about a Suggestion.

## Example Usage

```typescript
import { FeedbackArticleForSuggestion } from "@egain/egain-api-typescript/models";

let value: FeedbackArticleForSuggestion = {
  id: "PROD-3259",
  relatedArticles: [
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

| Field                                                                                                             | Type                                                                                                              | Required                                                                                                          | Description                                                                                                       | Example                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                              | *string*                                                                                                          | :heavy_minus_sign:                                                                                                | The ID of the Suggestion. A Suggestion ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-3259                                                                                                         |
| `name`                                                                                                            | *string*                                                                                                          | :heavy_minus_sign:                                                                                                | The name of the Suggestion.                                                                                       |                                                                                                                   |
| `relatedArticles`                                                                                                 | [models.ArticleResult](../models/articleresult.md)[]                                                              | :heavy_minus_sign:                                                                                                | Related Articles for the Suggestion.                                                                              |                                                                                                                   |