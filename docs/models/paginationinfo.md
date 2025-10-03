# PaginationInfo

## Example Usage

```typescript
import { PaginationInfo } from "@egain/egain-api-typescript/models";

let value: PaginationInfo = {
  count: 593004,
  pagenum: 910490,
  pagesize: 867739,
};
```

## Fields

| Field                                                                                   | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `count`                                                                                 | *number*                                                                                | :heavy_check_mark:                                                                      | The total number of pages.                                                              |
| `pagenum`                                                                               | *number*                                                                                | :heavy_check_mark:                                                                      | The page number requested. Page numbers start from 1.                                   |
| `pagesize`                                                                              | *number*                                                                                | :heavy_check_mark:                                                                      | The number of objects requested per page. The maximum number of objects per page is 75. |
| `link`                                                                                  | [models.Link](../models/link.md)[]                                                      | :heavy_minus_sign:                                                                      | Can include the *prev* and *next* link.                                                 |