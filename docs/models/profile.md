# Profile

## Example Usage

```typescript
import { Profile } from "@egain/egain-api-typescript/models";

let value: Profile = {
  id: "<id>",
  name: "<value>",
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *string*                                                                         | :heavy_check_mark:                                                               | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/> |
| `name`                                                                           | *string*                                                                         | :heavy_check_mark:                                                               | Name of the profile                                                              |