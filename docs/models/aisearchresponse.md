# AISearchResponse

## Example Usage

```typescript
import { AISearchResponse } from "@egain/egain-api-typescript/models";

let value: AISearchResponse = {
  searchResults: {
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
        articleTypeAttributes: {
          typeName: "General",
          articleTypeId: 243500000023393,
        },
        relevanceScore: 3941.01,
      },
    ],
  },
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `channel`                                                              | [models.AISearchResponseChannel](../models/aisearchresponsechannel.md) | :heavy_minus_sign:                                                     | N/A                                                                    |
| `searchResults`                                                        | [models.SearchResults](../models/searchresults.md)                     | :heavy_minus_sign:                                                     | Top search results with relevance scores                               |
| `paginationInfo`                                                       | [models.PaginationInfo](../models/paginationinfo.md)                   | :heavy_minus_sign:                                                     | N/A                                                                    |