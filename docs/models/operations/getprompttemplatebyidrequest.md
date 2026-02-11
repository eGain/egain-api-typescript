# GetPromptTemplateByIdRequest

## Example Usage

```typescript
import { GetPromptTemplateByIdRequest } from "@egain/egain-api-typescript/models/operations";

let value: GetPromptTemplateByIdRequest = {
  acceptLanguage: "en-US",
  department: "Service",
  languageCode: "en-US",
  promptID: "PROD-4582",
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `department`                                                                                                                    | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | Name of the department. Must be a valid department name.                                                                        | Service                                                                                                                         |
| `languageCode`                                                                                                                  | [operations.GetPromptTemplateByIdLanguageCode](../../models/operations/getprompttemplatebyidlanguagecode.md)                    | :heavy_check_mark:                                                                                                              | The language used while writing the prompt templates.                                                                           | en-US                                                                                                                           |
| `promptID`                                                                                                                      | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The promptID of the prompt template you want to fetch details for.                                                              | PROD-4582                                                                                                                       |