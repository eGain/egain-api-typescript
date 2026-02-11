# ExecutePromptRequest

## Example Usage

```typescript
import { ExecutePromptRequest } from "@egain/egain-api-typescript/models/operations";

let value: ExecutePromptRequest = {
  promptId: "<id>",
};
```

## Fields

| Field                                                                                            | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `promptId`                                                                                       | *string*                                                                                         | :heavy_check_mark:                                                                               | ID of the prompt template from the AI console. Only published and active prompt IDs are allowed. |
| `executePrompt`                                                                                  | [models.ExecutePrompt](../../models/executeprompt.md)                                            | :heavy_minus_sign:                                                                               | N/A                                                                                              |