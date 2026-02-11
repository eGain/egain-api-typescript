# CreateSuggestionLanguage

The knowledge base language in which the Suggestion is created.

## Example Usage

```typescript
import { CreateSuggestionLanguage } from "@egain/egain-api-typescript/models";

let value: CreateSuggestionLanguage = {
  code: "en-GB",
};
```

## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `code`                                                           | [models.CreateSuggestionCode](../models/createsuggestioncode.md) | :heavy_check_mark:                                               | The code of the language.                                        |