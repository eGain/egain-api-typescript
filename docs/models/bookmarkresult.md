# BookmarkResult

One or more instances of Bookmark.

## Example Usage

```typescript
import { BookmarkResult } from "@egain/egain-api-typescript/models";

let value: BookmarkResult = {
  bookmarks: [
    {
      portalId: "PROD-98123",
      resourceId: "DEV-7692",
      id: "1000001035",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `bookmarks`                                          | [models.Bookmark](../models/bookmark.md)[]           | :heavy_minus_sign:                                   | N/A                                                  |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |