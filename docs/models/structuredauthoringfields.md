# StructuredAuthoringFields

## Example Usage

```typescript
import { StructuredAuthoringFields } from "@egain/egain-api-typescript/models";

let value: StructuredAuthoringFields = {};
```

## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `confidenceLevel`                                                                   | [models.L10NString](../models/l10nstring.md)                                        | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `issue`                                                                             | *string*                                                                            | :heavy_minus_sign:                                                                  | Describes the problem, symptom, or question the article addresses.                  |
| `environment`                                                                       | *string*                                                                            | :heavy_minus_sign:                                                                  | Specifies the relevant product(s), category, or business process tied to the issue. |
| `cause`                                                                             | *string*                                                                            | :heavy_minus_sign:                                                                  | Identifies the underlying cause of the issue.                                       |