# ScheduleTime

## Example Usage

```typescript
import { ScheduleTime } from "@egain/egain-api-typescript/models";

let value: ScheduleTime = {
  date: new Date("2024-03-01T10:00:00.000Z"),
  stopDate: new Date("2024-03-01T14:00:00.000Z"),
};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    | Example                                                                                        |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `date`                                                                                         | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)  | :heavy_check_mark:                                                                             | The scheduled start time for the import job.                                                   | 2024-03-01T10:00:00.000Z                                                                       |
| `stopDate`                                                                                     | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)  | :heavy_minus_sign:                                                                             | The specific date and time when the job must stop processing, regardless of completion status. | 2024-03-01T14:00:00.000Z                                                                       |