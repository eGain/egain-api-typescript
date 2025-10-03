# UserProfile

## Example Usage

```typescript
import { UserProfile } from "@egain/egain-api-typescript/models";

let value: UserProfile = {};
```

## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `id`                                                                              | *string*                                                                          | :heavy_minus_sign:                                                                | The Readable ID of the user profile.<br><br/>                                     |
| `name`                                                                            | *string*                                                                          | :heavy_minus_sign:                                                                | Name given to the user profile                                                    |
| `isLastUsedInPortal`                                                              | *boolean*                                                                         | :heavy_minus_sign:                                                                | Indicates if the profile was the last one used by the current user in the portal. |