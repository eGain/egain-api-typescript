# ComplianceForArticle

This schema contains the compliance details for an Article.

## Example Usage

```typescript
import { ComplianceForArticle } from "@egain/egain-api-typescript/models";

let value: ComplianceForArticle = {};
```

## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `startDate`                                                      | [models.StartDateDateAndTime](../models/startdatedateandtime.md) | :heavy_minus_sign:                                               | The start date for the Article.                                  |
| `dueDate`                                                        | [models.DueDateDateAndTime](../models/duedatedateandtime.md)     | :heavy_minus_sign:                                               | The end date for the Article.                                    |