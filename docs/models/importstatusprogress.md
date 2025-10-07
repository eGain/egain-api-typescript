# ImportStatusProgress

Progress of the job.

## Example Usage

```typescript
import { ImportStatusProgress } from "@egain/egain-api-typescript/models";

let value: ImportStatusProgress = {};
```

## Fields

| Field                                               | Type                                                | Required                                            | Description                                         |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| `processed`                                         | *number*                                            | :heavy_minus_sign:                                  | Number of items processed.                          |
| `total`                                             | *number*                                            | :heavy_minus_sign:                                  | Number of total items to process.                   |
| `percentage`                                        | *number*                                            | :heavy_minus_sign:                                  | Percentage of total items that have been processed. |