# RejectGHSolutionRequest

## Example Usage

```typescript
import { RejectGHSolutionRequest } from "@egain/egain-api-typescript/models/operations";

let value: RejectGHSolutionRequest = {
  acceptLanguage: "en-US",
  portalID: "PROD-1000",
  caseID: "1000001085",
  quickpickRating: {
    id: "409601000000001",
    name: "<value>",
    profileId: "<id>",
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `portalID`                                                                                                                      | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the portal being accessed.<br><br>A portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-1000                                                                                                                       |
| `caseID`                                                                                                                        | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The numerical ID of the Case for which details is to be fetched.                                                                | 1000001085                                                                                                                      |
| `quickpickRating`                                                                                                               | [models.QuickpickRating](../../models/quickpickrating.md)                                                                       | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             |                                                                                                                                 |