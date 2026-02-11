# LastModifiedDateAndTime

Date of last modification.

## Example Usage

```typescript
import { LastModifiedDateAndTime } from "@egain/egain-api-typescript/models";

let value: LastModifiedDateAndTime = {
  date: new Date("2025-11-06T11:38:31.229Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `user`                                                                                        | [models.UserView](../models/userview.md)                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | The date in the format <code>YYYY-MM-DDTHH:MM:SS</code>.                                      |