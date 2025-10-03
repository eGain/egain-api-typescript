# AddToReplyRequest

## Example Usage

```typescript
import { AddToReplyRequest } from "@egain/egain-api-typescript/models/operations";

let value: AddToReplyRequest = {
  acceptLanguage: "en-US",
  portalID: "PROD-1000",
  articleID: "PROD-2996",
  articleActivityLink: {
    versionId: "PROD-12416",
    editionId: "PROD-13015",
    language: {
      code: "en-US",
    },
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `portalID`                                                                                                                      | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the portal being accessed.<br><br>A portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1000                                                                                                                       |
| `articleID`                                                                                                                     | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the Article.<br><br>An Article ID is composed of a 2-4 letter prefix followed by a dash and 4-15 digits.              | PROD-2996                                                                                                                       |
| `articleActivityLink`                                                                                                           | [models.ArticleActivityLink](../../models/articleactivitylink.md)                                                               | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             | {<br/>"editionId": "PROD-13015",<br/>"versionId": "PROD-12416",<br/>"language": {<br/>"code": "en-US"<br/>}<br/>}               |