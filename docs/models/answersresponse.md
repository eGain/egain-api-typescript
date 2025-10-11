# AnswersResponse

## Example Usage

```typescript
import { AnswersResponse } from "@egain/egain-api-typescript/models";

let value: AnswersResponse = {
  answer: {
    answerValue: "Per the lending FAQ document...",
    references: [],
    answerType: "certified",
    relevanceScore: 0.99,
  },
  searchResults: [],
  sessionId: "<id>",
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `answer`                                                                                                           | [models.AnswersResponseAnswer](../models/answersresponseanswer.md)                                                 | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |
| `searchResults`                                                                                                    | [models.SearchResult](../models/searchresult.md)[]                                                                 | :heavy_check_mark:                                                                                                 | List of top search results used to support the answer. Includes snippets, metadata, and relevance scores.          |
| `channel`                                                                                                          | [models.AnswersResponseChannel](../models/answersresponsechannel.md)                                               | :heavy_minus_sign:                                                                                                 | N/A                                                                                                                |
| `sessionId`                                                                                                        | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session. |
| `eventId`                                                                                                          | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | Unique ID for this specific API call or event.                                                                     |