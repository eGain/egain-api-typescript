# GetArticleEditionDetailsRequest

## Example Usage

```typescript
import { GetArticleEditionDetailsRequest } from "@egain/egain-api-typescript/models/operations";

let value: GetArticleEditionDetailsRequest = {
  acceptLanguage: "en-US",
  articleID: "PROD-2996",
  publishViewId: "PROD-3020",
  language: "en-US",
};
```

## Fields

| Field                                                                                                                            | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      | Example                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                 | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                          | :heavy_check_mark:                                                                                                               | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses).  | en-US                                                                                                                            |
| `articleID`                                                                                                                      | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | The ID of the Article. Both numeric and alternate ID formats are supported.<br><br>Valid numerical IDs are 15-19 digits long.    | PROD-2996                                                                                                                        |
| `publishViewId`                                                                                                                  | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | The ID of a Publish View Id.<br><br>A Publish View Id ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-3020                                                                                                                        |
| `language`                                                                                                                       | [models.MandatoryLanguageQueryParameter](../../models/mandatorylanguagequeryparameter.md)                                        | :heavy_check_mark:                                                                                                               | The language used for fetching the details of a resource. Resources available in different languages may differ from each other. | en-US                                                                                                                            |