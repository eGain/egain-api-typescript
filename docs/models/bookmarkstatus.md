# BookmarkStatus

Article Bookmark Status

## Example Usage

```typescript
import { BookmarkStatus } from "@egain/egain-api-typescript/models";

let value: BookmarkStatus = {
  isBookmarked: true,
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `isBookmarked`                                            | *boolean*                                                 | :heavy_check_mark:                                        | Indicates whether the Article is bookmarked               |
| `bookmarkID`                                              | *number*                                                  | :heavy_minus_sign:                                        | The ID of the Bookmark, if Article is bookmarked.         |
| `folderBreadcrumb`                                        | [models.FolderBreadcrumb](../models/folderbreadcrumb.md)  | :heavy_minus_sign:                                        | This schema contains one or more FolderSummary instances. |