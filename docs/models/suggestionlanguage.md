# SuggestionLanguage

The knowledge base language in which the Suggestion was created.

## Example Usage

```typescript
import { SuggestionLanguage } from "@egain/egain-api-typescript/models";

let value: SuggestionLanguage = {
  code: "es-ES",
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `code`                                                                                                                          | [models.SuggestionCode](../models/suggestioncode.md)                                                                            | :heavy_check_mark:                                                                                                              | The language that describes the details of the resource. Resources available in different languages may differ from each other. |
| `label`                                                                                                                         | [models.Label](../models/label.md)                                                                                              | :heavy_minus_sign:                                                                                                              | The name of the language.                                                                                                       |