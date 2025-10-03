# AddbookmarkRequest

## Example Usage

```typescript
import { AddbookmarkRequest } from "@egain/egain-api-typescript/models/operations";

let value: AddbookmarkRequest = {
  portalID: "PROD-1000",
  acceptLanguage: "en-US",
  createBookmark: {
    resourceId: "DEV-7692",
    userId: "1000001035",
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `portalID`                                                                                                                      | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the portal being accessed.<br><br>A portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1000                                                                                                                       |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `createBookmark`                                                                                                                | [models.CreateBookmark](../../models/createbookmark.md)                                                                         | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             |                                                                                                                                 |