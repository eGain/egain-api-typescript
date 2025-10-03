# Progress

Details about the job's progress.

## Example Usage

```typescript
import { Progress } from "@egain/egain-api-typescript/models";

let value: Progress = {
  processed: 1500,
  total: 4500,
  percentage: 30,
};
```

## Fields

| Field                                       | Type                                        | Required                                    | Description                                 | Example                                     |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `processed`                                 | *number*                                    | :heavy_minus_sign:                          | The number of items processed so far.       | 1500                                        |
| `total`                                     | *number*                                    | :heavy_minus_sign:                          | The total number of items to process.       | 4500                                        |
| `percentage`                                | *number*                                    | :heavy_minus_sign:                          | The percentage of the job that is complete. | 30                                          |