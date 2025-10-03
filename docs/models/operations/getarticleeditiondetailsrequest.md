# GetArticleEditionDetailsRequest

## Example Usage

```typescript
import { GetArticleEditionDetailsRequest } from "@egain/egain-api-typescript/models/operations";

let value: GetArticleEditionDetailsRequest = {
  acceptLanguage: "en-US",
  articleID: "<id>",
  publishViewId: "959500000204621",
  language: "en-US",
};
```

## Fields

| Field                                                                                                                            | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      | Example                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                 | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                          | :heavy_check_mark:                                                                                                               | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses).  | en-US                                                                                                                            |
| `articleID`                                                                                                                      | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | The ID of the Article. Both numeric and alternate ID formats are supported.<br><br>Valid numerical IDs are 15-19 digits long.    |                                                                                                                                  |
| `publishViewId`                                                                                                                  | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | Publish View Id of the article on which operation is performed.                                                                  | 959500000204621                                                                                                                  |
| `language`                                                                                                                       | [models.MandatoryLanguageQueryParameter](../../models/mandatorylanguagequeryparameter.md)                                        | :heavy_check_mark:                                                                                                               | The language used for fetching the details of a resource. Resources available in different languages may differ from each other. | en-US                                                                                                                            |