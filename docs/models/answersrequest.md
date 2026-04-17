# AnswersRequest

## Example Usage

```typescript
import { AnswersRequest } from "@egain/egain-api-typescript/models";

let value: AnswersRequest = {
  channel: {
    name: "Eight Bank Website",
  },
  eventId: "6154589f-b43f-4471-b2c7-92c6c888a643",
  clientSessionId: "6154589f-b43f-4471-b2c7-92c6c888a678",
  sessionId: "6154589f-b43f-4471-b2c7-92c6c888a651",
};
```

## Fields

| Field                                                                                                                            | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      | Example                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `channel`                                                                                                                        | [models.AnswersRequestChannel](../models/answersrequestchannel.md)                                                               | :heavy_minus_sign:                                                                                                               | N/A                                                                                                                              |                                                                                                                                  |
| `eventId`                                                                                                                        | *string*                                                                                                                         | :heavy_minus_sign:                                                                                                               | Unique ID for this specific API call or event.                                                                                   | 6154589f-b43f-4471-b2c7-92c6c888a643                                                                                             |
| `clientSessionId`                                                                                                                | *string*                                                                                                                         | :heavy_minus_sign:                                                                                                               | Session ID passed by the client for this specific API call or event.                                                             | 6154589f-b43f-4471-b2c7-92c6c888a678                                                                                             |
| `sessionId`                                                                                                                      | *string*                                                                                                                         | :heavy_minus_sign:                                                                                                               | eGain Session ID that ties multiple API calls to the same user session. Will be used as part of to tie events back to a session. | 6154589f-b43f-4471-b2c7-92c6c888a651                                                                                             |