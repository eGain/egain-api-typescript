# ExportStatus

## Example Usage

```typescript
import { ExportStatus } from "@egain/egain-api-typescript/models";

let value: ExportStatus = {
  status: "In Progress",
  progress: {
    processed: 1500,
    total: 4500,
    percentage: 30,
  },
  startTime: new Date("2025-09-15T10:00:00.000Z"),
  estimatedCompletion: new Date("2025-09-15T11:30:00.000Z"),
  completionTime: new Date("2025-09-15T11:25:00.000Z"),
  failureTime: new Date("2025-09-15T10:45:00.000Z"),
  results: {
    successful: 4485,
    warnings: 10,
    errors: 5,
  },
  error: "Connection timeout after processing 1500 items.",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `status`                                                                                      | [models.ExportStatusStatus](../models/exportstatusstatus.md)                                  | :heavy_check_mark:                                                                            | N/A                                                                                           | In Progress                                                                                   |
| `progress`                                                                                    | [models.ExportStatusProgress](../models/exportstatusprogress.md)                              | :heavy_minus_sign:                                                                            | Details about the job's progress.                                                             |                                                                                               |
| `startTime`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | The timestamp when the job started.                                                           | 2025-09-15T10:00:00.000Z                                                                      |
| `estimatedCompletion`                                                                         | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | The estimated timestamp when the job is expected to finish.                                   | 2025-09-15T11:30:00.000Z                                                                      |
| `completionTime`                                                                              | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | The timestamp when the job completed.                                                         | 2025-09-15T11:25:00.000Z                                                                      |
| `failureTime`                                                                                 | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | The timestamp when the job failed.                                                            | 2025-09-15T10:45:00.000Z                                                                      |
| `results`                                                                                     | [models.ExportStatusResults](../models/exportstatusresults.md)                                | :heavy_minus_sign:                                                                            | Breakdown of completed job results.                                                           |                                                                                               |
| `error`                                                                                       | *string*                                                                                      | :heavy_minus_sign:                                                                            | A description of the job failure reason.                                                      | Connection timeout after processing 1500 items.                                               |