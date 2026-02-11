# DueDateDateAndTime

The end date for the Article.

## Example Usage

```typescript
import { DueDateDateAndTime } from "@egain/egain-api-typescript/models";

let value: DueDateDateAndTime = {
  date: new Date("2024-06-12T23:14:45.901Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | The date in the format <code>YYYY-MM-DDTHH:MM:SS</code>.                                      |