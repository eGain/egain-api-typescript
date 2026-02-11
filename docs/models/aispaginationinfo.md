# AISPaginationInfo

## Example Usage

```typescript
import { AISPaginationInfo } from "@egain/egain-api-typescript/models";

let value: AISPaginationInfo = {};
```

## Fields

| Field                                                                                   | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `count`                                                                                 | *number*                                                                                | :heavy_minus_sign:                                                                      | The total number of pages.                                                              |
| `pagenum`                                                                               | *number*                                                                                | :heavy_minus_sign:                                                                      | The page number requested. Page numbers start from 1.                                   |
| `pagesize`                                                                              | *number*                                                                                | :heavy_minus_sign:                                                                      | The number of objects requested per page. The maximum number of objects per page is 75. |
| `link`                                                                                  | [models.Link](../models/link.md)[]                                                      | :heavy_minus_sign:                                                                      | Can include the *prev* and *next* link.                                                 |