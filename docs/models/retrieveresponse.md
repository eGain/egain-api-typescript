# RetrieveResponse

## Example Usage

```typescript
import { RetrieveResponse } from "@egain/egain-api-typescript/models";

let value: RetrieveResponse = {
  answer: {
    answerValue: "Per the Lending FAQ document...",
    references: [
      {
        id: "<id>",
        name: "<value>",
        docType: "PDF",
        source: "eGain Attachment",
        topicBreadcrumb: [
          {
            topicSummary: [
              {
                id: "PROD-1921",
              },
            ],
          },
        ],
      },
    ],
    answerType: "certified",
    relevanceScore: 0.99,
  },
  searchResults: [
    {
      id: "PROD-48192",
      name: "Lending FAQs",
      docType: "PPTX",
      source: "eGain Article",
      snippet: "Fair lending is a part of...",
      relevanceScore: 2629.42,
      topicBreadcrumb: [
        {
          topicSummary: [
            {
              id: "PROD-1921",
            },
          ],
        },
      ],
    },
  ],
  channel: {
    type: "custom",
    name: "Eight Bank Page",
  },
  eventId: "6154589f-b43f-4471-b2c7-92c6c888a871",
  sessionId: "6154589f-b43f-4471-b2c7-92c6c888a643",
};
```

## Fields

| Field                                                                                                                                                                                            | Type                                                                                                                                                                                             | Required                                                                                                                                                                                         | Description                                                                                                                                                                                      | Example                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `answer`                                                                                                                                                                                         | [models.RetrieveResponseAnswer](../models/retrieveresponseanswer.md)                                                                                                                             | :heavy_minus_sign:                                                                                                                                                                               | If a certified answer is given. The answer object will be present. <br><br> This will be shown only if certified answers are configured and the certified answer meets the configured threshold. |                                                                                                                                                                                                  |
| `searchResults`                                                                                                                                                                                  | [models.SearchResult](../models/searchresult.md)[]                                                                                                                                               | :heavy_check_mark:                                                                                                                                                                               | Top search results with relevance scores and metadata.                                                                                                                                           |                                                                                                                                                                                                  |
| `channel`                                                                                                                                                                                        | [models.RetrieveResponseChannel](../models/retrieveresponsechannel.md)                                                                                                                           | :heavy_minus_sign:                                                                                                                                                                               | N/A                                                                                                                                                                                              |                                                                                                                                                                                                  |
| `eventId`                                                                                                                                                                                        | *string*                                                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                               | Unique ID for this specific API call or event.                                                                                                                                                   | 6154589f-b43f-4471-b2c7-92c6c888a871                                                                                                                                                             |
| `sessionId`                                                                                                                                                                                      | *string*                                                                                                                                                                                         | :heavy_check_mark:                                                                                                                                                                               | ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session.                                                                               | 6154589f-b43f-4471-b2c7-92c6c888a643                                                                                                                                                             |