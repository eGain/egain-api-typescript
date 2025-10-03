# StartCustomerEscalationRequest

## Example Usage

```typescript
import { StartCustomerEscalationRequest } from "@egain/egain-api-typescript/models/operations";

let value: StartCustomerEscalationRequest = {
  acceptLanguage: "en-US",
  portalID: "PROD-1000",
  language: "en-US",
  startEscalationRequest: {
    subject: "<value>",
    body: "<value>",
    channel: "email",
    url: "https://valuable-morbidity.info/",
  },
};
```

## Fields

| Field                                                                                                                            | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      | Example                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                 | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                          | :heavy_check_mark:                                                                                                               | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses).  | en-US                                                                                                                            |
| `portalID`                                                                                                                       | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | The ID of the portal being accessed.<br><br>A portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits.  | PROD-1000                                                                                                                        |
| `language`                                                                                                                       | [models.MandatoryLanguageQueryParameter](../../models/mandatorylanguagequeryparameter.md)                                        | :heavy_check_mark:                                                                                                               | The language used for fetching the details of a resource. Resources available in different languages may differ from each other. | en-US                                                                                                                            |
| `startEscalationRequest`                                                                                                         | [models.StartEscalationRequest](../../models/startescalationrequest.md)                                                          | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |                                                                                                                                  |