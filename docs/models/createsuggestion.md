# CreateSuggestion

This schema contains information about a Suggestion.

## Example Usage

```typescript
import { CreateSuggestion } from "@egain/egain-api-typescript/models";

let value: CreateSuggestion = {
  name: "<value>",
  content: "<value>",
  feedbackArticle: {
    id: "PROD-9821",
  },
  language: {
    code: "pt-PT",
  },
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `name`                                                                                                             | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | The name of the Suggestion.                                                                                        |
| `description`                                                                                                      | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | The description of the Suggestion.                                                                                 |
| `content`                                                                                                          | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | The content of the Suggestion.                                                                                     |
| `feedbackArticle`                                                                                                  | [models.RelatedArticleForCreateUpdateDeleteSuggestion](../models/relatedarticleforcreateupdatedeletesuggestion.md) | :heavy_minus_sign:                                                                                                 | The Article that the Suggestion was created for.                                                                   |
| `attachments`                                                                                                      | [models.CreateSuggestionAttachments](../models/createsuggestionattachments.md)                                     | :heavy_minus_sign:                                                                                                 | Details of Attachments for the Suggestion.                                                                         |
| `language`                                                                                                         | [models.CreateSuggestionLanguage](../models/createsuggestionlanguage.md)                                           | :heavy_check_mark:                                                                                                 | The knowledge base language in which the Suggestion is created.                                                    |
| `customAttributes`                                                                                                 | [models.CustomAttribute](../models/customattribute.md)[]                                                           | :heavy_minus_sign:                                                                                                 | The Custom Attributes of the Suggestion.                                                                           |