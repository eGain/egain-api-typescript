# ArticleSearchResult

Article search result.

## Example Usage

```typescript
import { ArticleSearchResult } from "@egain/egain-api-typescript/models";

let value: ArticleSearchResult = {
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
};
```

## Fields

| Field                                                                                                            | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                             | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The ID of the Article.<br>An Article ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits.  |
| `additionalInfo`                                                                                                 | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | Additional information about the Article. Max 1 KB.                                                              |
| `articleMacro`                                                                                                   | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The name of the macro associated with this Article.                                                              |
| `articleType`                                                                                                    | [models.ArticleType](../models/articletype.md)                                                                   | :heavy_minus_sign:                                                                                               | The type of the Article and its attributes.                                                                      |
| `articleKeywords`                                                                                                | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | A comma-separated list of keywords associated with this Article. 1 KB max size limit.                            |
| `articleSummary`                                                                                                 | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | A brief summary of the Article, provided as metadata. 1 KB max size limit.                                       |
| `availabilityDate`                                                                                               | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The date on which the Article version is available.                                                              |
| `availableEditions`                                                                                              | [models.Edition](../models/edition.md)[]                                                                         | :heavy_minus_sign:                                                                                               | The editions of this Article that are available to the user.                                                     |
| `averageRating`                                                                                                  | *number*                                                                                                         | :heavy_minus_sign:                                                                                               | The average rating of the Article.                                                                               |
| `createdBy`                                                                                                      | [models.CreatedBy](../models/createdby.md)                                                                       | :heavy_minus_sign:                                                                                               | N/A                                                                                                              |
| `modifiedBy`                                                                                                     | [models.ModifiedBy](../models/modifiedby.md)                                                                     | :heavy_minus_sign:                                                                                               | N/A                                                                                                              |
| `ownedBy`                                                                                                        | [models.OwnedBy](../models/ownedby.md)                                                                           | :heavy_minus_sign:                                                                                               | N/A                                                                                                              |
| `createdDate`                                                                                                    | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | N/A                                                                                                              |
| `customAttributes`                                                                                               | [models.CustomAttribute](../models/customattribute.md)[]                                                         | :heavy_minus_sign:                                                                                               | A list of custom attributes.                                                                                     |
| `departmentID`                                                                                                   | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | ID of the Article's department.                                                                                  |
| `description`                                                                                                    | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | A description of the Article. The maximum allowed Article description size is 1 KB.                              |
| `expirationDate`                                                                                                 | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | Date of Article expiration if Article expires otherwise empty.                                                   |
| `hasAttachments`                                                                                                 | *boolean*                                                                                                        | :heavy_minus_sign:                                                                                               | Indicates whether the Article has any attachments.                                                               |
| `imageURL`                                                                                                       | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The URL of an image to be associated with the Article.                                                           |
| `includeInGenAI`                                                                                                 | *boolean*                                                                                                        | :heavy_minus_sign:                                                                                               | Indicates whether the Article is included for Generative AI.                                                     |
| `isSubscribed`                                                                                                   | *boolean*                                                                                                        | :heavy_minus_sign:                                                                                               | Indicates whether the Article is subscribed for notifications.                                                   |
| `modifiedDate`                                                                                                   | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The date on which the Article was last modified.                                                                 |
| `languageCode`                                                                                                   | [models.LanguageCode](../models/languagecode.md)                                                                 | :heavy_minus_sign:                                                                                               | Language code of the resource's language.                                                                        |
| `link`                                                                                                           | [models.Link](../models/link.md)                                                                                 | :heavy_minus_sign:                                                                                               | Defines the relationship between this resource and another object.                                               |
| `name`                                                                                                           | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The name of the Article.                                                                                         |
| `snippet`                                                                                                        | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | A returned matching snippet within article content when searching for a search term.                             |
| `snippetForStructuredAuthoring`                                                                                  | [models.SnippetForStructuredAuthoring](../models/snippetforstructuredauthoring.md)                               | :heavy_minus_sign:                                                                                               | N/A                                                                                                              |
| `articleState`                                                                                                   | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The Article's state.                                                                                             |
| `timesRated`                                                                                                     | *number*                                                                                                         | :heavy_minus_sign:                                                                                               | The number of times that this Article has been rated.                                                            |
| `topicBreadcrumb`                                                                                                | [models.TopicBreadcrumb](../models/topicbreadcrumb.md)[]                                                         | :heavy_minus_sign:                                                                                               | A list of topics from the root topic to this Article. There may be multiple paths.                               |
| `versionId`                                                                                                      | *string*                                                                                                         | :heavy_minus_sign:                                                                                               | The ID of this version of the Article.                                                                           |
| `workflow`                                                                                                       | [models.Workflow](../models/workflow.md)                                                                         | :heavy_minus_sign:                                                                                               | The Article's workflow.                                                                                          |
| `compliance`                                                                                                     | [models.ComplianceForArticle](../models/complianceforarticle.md)                                                 | :heavy_minus_sign:                                                                                               | This schema contains the compliance details for an Article.                                                      |
| `personalization`                                                                                                | [models.Personalization](../models/personalization.md)                                                           | :heavy_minus_sign:                                                                                               | Personalization allows the filtering of search results and controls the access to articles and article editions. |