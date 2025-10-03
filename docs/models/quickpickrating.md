# QuickpickRating

## Example Usage

```typescript
import { QuickpickRating } from "@egain/egain-api-typescript/models";

let value: QuickpickRating = {
  id: "409601000000001",
  name: "<value>",
  profileId: "<id>",
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      | Example                                                                          |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *string*                                                                         | :heavy_check_mark:                                                               | The numerical ID of the Casebase Release.                                        | 409601000000001                                                                  |
| `name`                                                                           | *string*                                                                         | :heavy_check_mark:                                                               | name of the case or article                                                      |                                                                                  |
| `profileId`                                                                      | *string*                                                                         | :heavy_check_mark:                                                               | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/> |                                                                                  |