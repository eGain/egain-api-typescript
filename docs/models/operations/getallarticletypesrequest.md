# GetAllArticleTypesRequest

## Example Usage

```typescript
import { GetAllArticleTypesRequest } from "@egain/egain-api-typescript/models/operations";

let value: GetAllArticleTypesRequest = {
  acceptLanguage: "en-US",
  departmentID: "999",
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `departmentID`                                                                                                                  | *string*                                                                                                                        | :heavy_check_mark:                                                                                                              | The ID of the department.                                                                                                       | 999                                                                                                                             |