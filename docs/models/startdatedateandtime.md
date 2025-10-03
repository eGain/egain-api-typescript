# StartDateDateAndTime

The start date for the Article.

## Example Usage

```typescript
import { StartDateDateAndTime } from "@egain/egain-api-typescript/models";

let value: StartDateDateAndTime = {
  date: new Date("2025-11-16T08:50:02.141Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | The date in the format <code>YYYY-MM-DDTHH:MM:SS</code>.                                      |