# ArticlePermissions

User permissions on the parent folder.

## Example Usage

```typescript
import { ArticlePermissions } from "@egain/egain-api-typescript/models";

let value: ArticlePermissions = {};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `view`                                                   | *boolean*                                                | :heavy_minus_sign:                                       | User has 'View Folder' permission on the parent folder.  |
| `edit`                                                   | *boolean*                                                | :heavy_minus_sign:                                       | User has 'Edit Article' permission on the parent folder. |