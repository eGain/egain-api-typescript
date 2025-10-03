# ArticlePermissionsResult

User permissions on the parent folder.

## Example Usage

```typescript
import { ArticlePermissionsResult } from "@egain/egain-api-typescript/models";

let value: ArticlePermissionsResult = {
  articleID: "EGSP-2433",
};
```

## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  | Example                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `articleID`                                                  | *string*                                                     | :heavy_minus_sign:                                           | ID of Article                                                | EGSP-2433                                                    |
| `permissions`                                                | [models.ArticlePermissions](../models/articlepermissions.md) | :heavy_minus_sign:                                           | User permissions on the parent folder.                       |                                                              |