# ReferenceResponseLink

Defines the relationship between this resource and another object.

## Example Usage

```typescript
import { ReferenceResponseLink } from "@egain/egain-api-typescript/models";

let value: ReferenceResponseLink = {};
```

## Fields

| Field                                                                                                                                                             | Type                                                                                                                                                              | Required                                                                                                                                                          | Description                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `rel`                                                                                                                                                             | *string*                                                                                                                                                          | :heavy_minus_sign:                                                                                                                                                | Defines the relationship between a linked resource and the current object. <br><br> For example: self, prev, next or an object name such as 'user', 'folder' etc. |
| `href`                                                                                                                                                            | *string*                                                                                                                                                          | :heavy_minus_sign:                                                                                                                                                | The URL that specifies the link's destination.                                                                                                                    |