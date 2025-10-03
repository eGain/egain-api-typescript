# AnswersResponse

## Example Usage

```typescript
import { AnswersResponse } from "@egain/egain-api-typescript/models";

let value: AnswersResponse = {
  searchResults: [
    {
      id: "PROD-48192",
      name: "Lending FAQs",
      docType: "Pdf",
      source: "eGain Attachment",
      snippet: "Fair lending is a part of...",
      relevanceScore: 2545.64,
    },
  ],
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `answer`                                                                                                           | [models.AnswersResponseAnswer](../models/answersresponseanswer.md)                                                 | :heavy_minus_sign:                                                                                                 | N/A                                                                                                                |
| `searchResults`                                                                                                    | [models.SearchResult](../models/searchresult.md)[]                                                                 | :heavy_minus_sign:                                                                                                 | List of top search results used to support the answer. Includes snippets, metadata, and relevance scores.          |
| `channel`                                                                                                          | [models.AnswersResponseChannel](../models/answersresponsechannel.md)                                               | :heavy_minus_sign:                                                                                                 | N/A                                                                                                                |
| `sessionId`                                                                                                        | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session. |
| `eventId`                                                                                                          | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | Unique ID for this specific API call or event.                                                                     |