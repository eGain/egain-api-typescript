# ImportContent

## Example Usage

```typescript
import { ImportContent } from "@egain/egain-api-typescript/models";

let value: ImportContent = {
  dataSource: {
    type: "Shared file path",
    path: "https://stiff-hepatitis.net",
  },
  operation: "reimport",
  scheduleTime: {
    date: new Date("2024-03-01T10:00:00.000Z"),
  },
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `dataSource`                                                           | [models.ImportContentDataSource](../models/importcontentdatasource.md) | :heavy_check_mark:                                                     | N/A                                                                    |
| `operation`                                                            | [models.Operation](../models/operation.md)                             | :heavy_check_mark:                                                     | N/A                                                                    |
| `scheduleTime`                                                         | [models.ScheduleTime](../models/scheduletime.md)                       | :heavy_minus_sign:                                                     | N/A                                                                    |