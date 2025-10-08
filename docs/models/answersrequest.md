# AnswersRequest

## Example Usage

```typescript
import { AnswersRequest } from "@egain/egain-api-typescript/models";

let value: AnswersRequest = {};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `channel`                                                                                                          | [models.AnswersRequestChannel](../models/answersrequestchannel.md)                                                 | :heavy_minus_sign:                                                                                                 | N/A                                                                                                                |
| `eventId`                                                                                                          | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | Unique ID for this specific API call or event.                                                                     |
| `sessionId`                                                                                                        | *string*                                                                                                           | :heavy_minus_sign:                                                                                                 | ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session. |