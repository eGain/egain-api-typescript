# CaseSearch

## Example Usage

```typescript
import { CaseSearch } from "@egain/egain-api-typescript/models";

let value: CaseSearch = {
  action: [
    {
      articleType: {
        articleTypeId: "932100000002020",
      },
    },
  ],
};
```

## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `acceptCount`                                                   | *number*                                                        | :heavy_minus_sign:                                              | The number of times action was accepted                         |
| `action`                                                        | [models.Action](../models/action.md)[]                          | :heavy_minus_sign:                                              | actions in search                                               |
| `additionalInfo`                                                | *boolean*                                                       | :heavy_minus_sign:                                              | This field indicates if action has additional information       |
| `metadata`                                                      | [models.Metadata](../models/metadata.md)[]                      | :heavy_minus_sign:                                              | Metadata in search                                              |
| `caseId`                                                        | *string*                                                        | :heavy_minus_sign:                                              | case Id                                                         |
| `passedThresholdValue`                                          | *boolean*                                                       | :heavy_minus_sign:                                              | This field indicates if the case has passed the threshold value |
| `rejectCount`                                                   | *number*                                                        | :heavy_minus_sign:                                              | The number of times action was rejected                         |
| `shortName`                                                     | *string*                                                        | :heavy_minus_sign:                                              | The short name                                                  |
| `score`                                                         | *number*                                                        | :heavy_minus_sign:                                              | The score of the case                                           |
| `title`                                                         | *string*                                                        | :heavy_minus_sign:                                              | The title of the case                                           |
| `type`                                                          | [models.CaseSearchType](../models/casesearchtype.md)            | :heavy_minus_sign:                                              | The type of the action                                          |