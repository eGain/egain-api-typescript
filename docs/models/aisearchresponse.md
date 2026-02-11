# AISearchResponse

## Example Usage

```typescript
import { AISearchResponse } from "@egain/egain-api-typescript/models";

let value: AISearchResponse = {
  searchResults: {
    article: [
      {
        id: "PROD-2996",
        name: "Fair Lending FAQs",
        docType: "PDF",
        docName: "Lending FAQs",
        source: "eGain Article",
        customAttributes: [
          {
            name: "loan_id",
            value: [
              "78391",
            ],
            type: "STRING",
          },
        ],
        snippet: "What is fair lending...",
        keywordSnippet: "What is fair lending...",
        additionalSnippets: [
          {
            id: "PROD-2996",
            name: "Fair Lending FAQs",
            docType: "DOCX",
            docName: "Banking FAQs",
            snippet: "The following Banking FAQs...",
            keywordSnippet: "The following Banking FAQs...",
            relevanceScore: 0.7,
            normalizedScore: 0.9,
          },
        ],
        additionalSnippetCount: 1,
        contextualSummary: "The summary of the lending FAQ...",
        modifiedDate: "2025-01-28T19:53:58Z",
        headerPath: "FAQs",
        topicBreadcrumb: [],
        articleTypeAttributes: {
          typeName: "General",
          articleTypeId: 243500000023393,
        },
        relevanceScore: 0.8,
        normalizedScore: 0.9,
      },
    ],
  },
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `searchResults`                                            | [models.SearchResults](../models/searchresults.md)         | :heavy_check_mark:                                         | Top search results with relevance scores                   |
| `paginationInfo`                                           | [models.AISPaginationInfo](../models/aispaginationinfo.md) | :heavy_minus_sign:                                         | N/A                                                        |