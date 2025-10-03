# CreateViewedSearchResultsEventForConnectorsRequest

## Example Usage

```typescript
import { CreateViewedSearchResultsEventForConnectorsRequest } from "@egain/egain-api-typescript/models/operations";

let value: CreateViewedSearchResultsEventForConnectorsRequest = {
  acceptLanguage: "en-US",
  portalID: "PROD-1000",
  createViewedSearchResultEventForConnectors: {
    languageCode: "da-DK",
    q: "India",
    url: "https://egain.com/",
    title: "Welcome to India",
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `portalID`                                                                                                                      | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the portal being accessed.<br><br>A portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1000                                                                                                                       |
| `createViewedSearchResultEventForConnectors`                                                                                    | [models.CreateViewedSearchResultEventForConnectors](../../models/createviewedsearchresulteventforconnectors.md)                 | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             |                                                                                                                                 |