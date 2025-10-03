# PublishProfile

This schema contains information about Profile.

## Example Usage

```typescript
import { PublishProfile } from "@egain/egain-api-typescript/models";

let value: PublishProfile = {
  id: "<id>",
  name: "<value>",
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *string*                                                                         | :heavy_check_mark:                                                               | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/> |
| `name`                                                                           | *string*                                                                         | :heavy_check_mark:                                                               | The name of the profile.                                                         |