# ShortURL

## Example Usage

```typescript
import { ShortURL } from "@egain/egain-api-typescript/models";

let value: ShortURL = {};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                            | *string*                                                                                                                        | :heavy_minus_sign:                                                                                                              | The alphanumeric ID of the short URL.<br><br>A topic ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `templateName`                                                                                                                  | *string*                                                                                                                        | :heavy_minus_sign:                                                                                                              | Name of template                                                                                                                |
| `shortURLName`                                                                                                                  | *string*                                                                                                                        | :heavy_minus_sign:                                                                                                              | Name of ShortURL                                                                                                                |
| `isDefault`                                                                                                                     | *boolean*                                                                                                                       | :heavy_minus_sign:                                                                                                              | N/A                                                                                                                             |