# CreatedDateAndTime

Date the Tag Category was created.

## Example Usage

```typescript
import { CreatedDateAndTime } from "@egain/egain-api-typescript/models";

let value: CreatedDateAndTime = {
  date: new Date("2023-10-30T11:01:49.391Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `user`                                                                                        | [models.UserView](../models/userview.md)                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | The date in the format <code>YYYY-MM-DDTHH:MM:SS</code>.                                      |