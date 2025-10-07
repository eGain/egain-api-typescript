# ImportStatusResults

Result of job.

## Example Usage

```typescript
import { ImportStatusResults } from "@egain/egain-api-typescript/models";

let value: ImportStatusResults = {};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `succesfull`                                 | *number*                                     | :heavy_minus_sign:                           | Number of item succesfully processed by job. |
| `warnings`                                   | *number*                                     | :heavy_minus_sign:                           | Number of warnings encountered during job.   |
| `errors`                                     | *number*                                     | :heavy_minus_sign:                           | Number of errors encountered during job.     |