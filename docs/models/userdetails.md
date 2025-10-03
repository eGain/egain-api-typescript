# UserDetails

Success

## Example Usage

```typescript
import { UserDetails } from "@egain/egain-api-typescript/models";

let value: UserDetails = {
  firstName: "John",
  lastName: "Doe",
};
```

## Fields

| Field                              | Type                               | Required                           | Description                        | Example                            |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `id`                               | *string*                           | :heavy_minus_sign:                 | The numerical ID of the User       |                                    |
| `roles`                            | [models.Role](../models/role.md)[] | :heavy_minus_sign:                 | Roles of the User                  |                                    |
| `firstName`                        | *string*                           | :heavy_minus_sign:                 | First Name of the User             | John                               |
| `lastName`                         | *string*                           | :heavy_minus_sign:                 | Last Name of the User              | Doe                                |
| `hasEmailConfigured`               | *boolean*                          | :heavy_minus_sign:                 | Indicates if user has email        |                                    |