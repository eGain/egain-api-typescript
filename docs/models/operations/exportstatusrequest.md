# ExportStatusRequest

## Example Usage

```typescript
import { ExportStatusRequest } from "@egain/egain-api-typescript/models/operations";

let value: ExportStatusRequest = {
  acceptLanguage: "en-US",
  jobID: "7A84B875-6F75-4C7B-B137-0632B62DB0BD",
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `jobID`                                                                                                                         | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | **Example Usage:**<br/>```bash<br/>GET /content/export/7A84B875-6F75-4C7B-B137-0632B62DB0BD/status<br/>```<br/>                 | 7A84B875-6F75-4C7B-B137-0632B62DB0BD                                                                                            |