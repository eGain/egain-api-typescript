# ExecutePromptResponse

## Example Usage

```typescript
import { ExecutePromptResponse } from "@egain/egain-api-typescript/models";

let value: ExecutePromptResponse = {
  generatedResponse: "Customer enquired about the order status...",
  eventType: "generate",
  sessionId: "79e43699-c210-49cd-b512-05607f727b98",
  clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
  sessionStatus: "active",
  eventRegistration: "successful",
};
```

## Fields

| Field                                                                                 | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `generatedResponse`                                                                   | *string*                                                                              | :heavy_check_mark:                                                                    | Final response from the LLM. If streaming is enabled, this contains a streaming link. | Customer enquired about the order status...                                           |
| `eventType`                                                                           | [models.ExecutePromptResponseEventType](../models/executepromptresponseeventtype.md)  | :heavy_check_mark:                                                                    | N/A                                                                                   | generate                                                                              |
| `sessionId`                                                                           | *string*                                                                              | :heavy_check_mark:                                                                    | N/A                                                                                   | 79e43699-c210-49cd-b512-05607f727b98                                                  |
| `clientSessionId`                                                                     | *string*                                                                              | :heavy_minus_sign:                                                                    | Client provided sessionID to store events against.                                    | 123e4567-e89b-12d3-a456-426614174000                                                  |
| `sessionStatus`                                                                       | [models.SessionStatus](../models/sessionstatus.md)                                    | :heavy_check_mark:                                                                    | N/A                                                                                   | active                                                                                |
| `eventRegistration`                                                                   | [models.EventRegistration](../models/eventregistration.md)                            | :heavy_check_mark:                                                                    | N/A                                                                                   | successful                                                                            |