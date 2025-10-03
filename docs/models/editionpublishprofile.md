# EditionPublishProfile

The publish view associated with this edition.

## Example Usage

```typescript
import { EditionPublishProfile } from "@egain/egain-api-typescript/models";

let value: EditionPublishProfile = {
  id: "<id>",
  name: "<value>",
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *string*                                                                         | :heavy_check_mark:                                                               | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/> |
| `name`                                                                           | *string*                                                                         | :heavy_check_mark:                                                               | The name of the profile.                                                         |