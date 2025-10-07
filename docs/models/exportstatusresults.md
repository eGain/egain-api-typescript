# ExportStatusResults

Breakdown of completed job results.

## Example Usage

```typescript
import { ExportStatusResults } from "@egain/egain-api-typescript/models";

let value: ExportStatusResults = {
  successful: 4485,
  warnings: 10,
  errors: 5,
};
```

## Fields

| Field                                      | Type                                       | Required                                   | Description                                | Example                                    |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `successful`                               | *number*                                   | :heavy_minus_sign:                         | The count of successfully processed items. | 4485                                       |
| `warnings`                                 | *number*                                   | :heavy_minus_sign:                         | The count of items with warnings.          | 10                                         |
| `errors`                                   | *number*                                   | :heavy_minus_sign:                         | The count of items with errors.            | 5                                          |