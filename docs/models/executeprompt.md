# ExecutePrompt

## Example Usage

```typescript
import { ExecutePrompt } from "@egain/egain-api-typescript/models";

let value: ExecutePrompt = {
  department: "Service",
  languageCode: "en-US",
  clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            | Example                                                                |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `department`                                                           | *string*                                                               | :heavy_check_mark:                                                     | Name of the department. Must be a valid department name.               | Service                                                                |
| `languageCode`                                                         | [models.LanguageCodeRequestBody](../models/languagecoderequestbody.md) | :heavy_check_mark:                                                     | The language used for the prompt template.                             | en-US                                                                  |
| `replacements`                                                         | *models.Replacement*[]                                                 | :heavy_minus_sign:                                                     | List of variable replacements (either static or search).               |                                                                        |
| `eventType`                                                            | [models.EventTypeRequestBody](../models/eventtyperequestbody.md)       | :heavy_minus_sign:                                                     | Event type logged when the API executes successfully.                  | generate                                                               |
| `clientSessionId`                                                      | *string*                                                               | :heavy_minus_sign:                                                     | Client provided sessionID to store events against.                     | 123e4567-e89b-12d3-a456-426614174000                                   |
| `streaming`                                                            | *boolean*                                                              | :heavy_minus_sign:                                                     | Whether to stream the response instead of returning inline.            | false                                                                  |