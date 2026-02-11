# AnswersResponse

## Example Usage

```typescript
import { AnswersResponse } from "@egain/egain-api-typescript/models";

let value: AnswersResponse = {
  answer: {
    answerValue: "The fair lending procedure...",
    references: [],
    answerType: "certified",
    relevanceScore: 0.99,
  },
  searchResults: [],
  channel: {
    type: "custom",
    name: "Eight Bank Website",
  },
  eventId: "6154589f-b43f-4471-b2c7-92c6c888a664",
  clientSessionId: "6154589f-b43f-4471-b2c7-92c6c888a643",
  sessionId: "6154589f-b43f-4471-b2c7-92c6c888a689",
};
```

## Fields

| Field                                                                                                                            | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      | Example                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `answer`                                                                                                                         | [models.AnswersResponseAnswer](../models/answersresponseanswer.md)                                                               | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |                                                                                                                                  |
| `searchResults`                                                                                                                  | [models.SearchResult](../models/searchresult.md)[]                                                                               | :heavy_check_mark:                                                                                                               | List of top search results used to support the answer. Includes snippets, metadata, and relevance scores.                        |                                                                                                                                  |
| `channel`                                                                                                                        | [models.AnswersResponseChannel](../models/answersresponsechannel.md)                                                             | :heavy_minus_sign:                                                                                                               | N/A                                                                                                                              |                                                                                                                                  |
| `eventId`                                                                                                                        | *string*                                                                                                                         | :heavy_minus_sign:                                                                                                               | Unique ID for this specific API call or event.                                                                                   | 6154589f-b43f-4471-b2c7-92c6c888a664                                                                                             |
| `clientSessionId`                                                                                                                | *string*                                                                                                                         | :heavy_minus_sign:                                                                                                               | Session ID passed by the client for this specific API call or event.                                                             | 6154589f-b43f-4471-b2c7-92c6c888a643                                                                                             |
| `sessionId`                                                                                                                      | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | eGain Session ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session. | 6154589f-b43f-4471-b2c7-92c6c888a689                                                                                             |