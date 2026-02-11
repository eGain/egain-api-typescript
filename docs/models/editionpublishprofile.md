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

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                            | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the Publish Profile.<br>An Publish Profile ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `name`                                                                                                                          | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The name of the profile.                                                                                                        |