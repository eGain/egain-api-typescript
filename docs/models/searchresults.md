# SearchResults

Top search results with relevance scores

## Example Usage

```typescript
import { SearchResults } from "@egain/egain-api-typescript/models";

let value: SearchResults = {
  article: [
    {
      id: "<id>",
      name: "<value>",
      docType: "HTML",
      source: "eGain Attachment",
      snippet: "<value>",
      topicBreadcrumb: [
        {
          topicSummary: [
            {
              id: "PROD-1921",
            },
          ],
        },
      ],
      relevanceScore: 3941.01,
    },
  ],
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `article`                                                            | [models.ArticleAISearchResult](../models/articleaisearchresult.md)[] | :heavy_minus_sign:                                                   | N/A                                                                  |
| `topic`                                                              | [models.TopicAISearchResult](../models/topicaisearchresult.md)[]     | :heavy_minus_sign:                                                   | N/A                                                                  |