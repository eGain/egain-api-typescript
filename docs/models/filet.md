# FileT

## Example Usage

```typescript
import { FileT } from "@egain/egain-api-typescript/models";

let value: FileT = {
  name: "<value>",
  content: "<value>",
};
```

## Fields

| Field                              | Type                               | Required                           | Description                        |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `name`                             | *string*                           | :heavy_check_mark:                 | Filename (e.g., script.js).        |
| `content`                          | *string*                           | :heavy_check_mark:                 | Base64 encoded JavaScript content. |
| `contentUrl`                       | *string*                           | :heavy_minus_sign:                 | N/A                                |