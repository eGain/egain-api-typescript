# SnippetForStructuredAuthoring

## Example Usage

```typescript
import { SnippetForStructuredAuthoring } from "@egain/egain-api-typescript/models";

let value: SnippetForStructuredAuthoring = {};
```

## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `issue`                                                                             | *string*                                                                            | :heavy_minus_sign:                                                                  | Describes the problem, symptom, or question the article addresses                   |
| `environment`                                                                       | *string*                                                                            | :heavy_minus_sign:                                                                  | Specifies the relevant product(s), category, or business process tied to the issue. |
| `cause`                                                                             | *string*                                                                            | :heavy_minus_sign:                                                                  | Identifies the underlying cause of the issue.                                       |