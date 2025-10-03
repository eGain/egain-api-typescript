# Case

Success

## Example Usage

```typescript
import { Case } from "@egain/egain-api-typescript/models";

let value: Case = {
  id: "100000000001035",
  releaseId: "100000000001035",
  clusterId: "100000000001035",
  action: [
    {
      articleType: {
        articleTypeId: "932100000002020",
      },
    },
  ],
  questionDetail: [
    {
      question: {
        id: "1000001035",
      },
      answer: [],
    },
  ],
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      | Example                                                                          |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *string*                                                                         | :heavy_minus_sign:                                                               | The numerical ID of the case.                                                    | 100000000001035                                                                  |
| `shortName`                                                                      | *string*                                                                         | :heavy_minus_sign:                                                               | short name of the case.                                                          |                                                                                  |
| `title`                                                                          | *string*                                                                         | :heavy_minus_sign:                                                               | title of the case                                                                |                                                                                  |
| `comments`                                                                       | *string*                                                                         | :heavy_minus_sign:                                                               | comments on the case                                                             |                                                                                  |
| `profileId`                                                                      | *string*                                                                         | :heavy_minus_sign:                                                               | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/> |                                                                                  |
| `releaseId`                                                                      | *string*                                                                         | :heavy_minus_sign:                                                               | The numerical ID of the Casebase Release in which case in created                | 100000000001035                                                                  |
| `clusterId`                                                                      | *string*                                                                         | :heavy_minus_sign:                                                               | ID of the cluster in which case is created                                       | 100000000001035                                                                  |
| `createdDate`                                                                    | *string*                                                                         | :heavy_minus_sign:                                                               | The date on which the Case was created.                                          |                                                                                  |
| `createdBy`                                                                      | [models.CreatedBy](../models/createdby.md)                                       | :heavy_minus_sign:                                                               | N/A                                                                              |                                                                                  |
| `modifiedBy`                                                                     | [models.ModifiedBy](../models/modifiedby.md)                                     | :heavy_minus_sign:                                                               | N/A                                                                              |                                                                                  |
| `modifiedDate`                                                                   | *string*                                                                         | :heavy_minus_sign:                                                               | The date on which the Case was last modified.                                    |                                                                                  |
| `isVisible`                                                                      | *boolean*                                                                        | :heavy_minus_sign:                                                               | Flag indicating if the case is visible                                           |                                                                                  |
| `rejectCount`                                                                    | *number*                                                                         | :heavy_minus_sign:                                                               | number of times case was rejected.                                               |                                                                                  |
| `acceptCount`                                                                    | *number*                                                                         | :heavy_minus_sign:                                                               | number of times case was accepted.                                               |                                                                                  |
| `action`                                                                         | [models.Action](../models/action.md)[]                                           | :heavy_minus_sign:                                                               | actions in the case                                                              |                                                                                  |
| `metadata`                                                                       | [models.Metadata](../models/metadata.md)[]                                       | :heavy_minus_sign:                                                               | Metadata of the case                                                             |                                                                                  |
| `thresholdValue`                                                                 | *number*                                                                         | :heavy_minus_sign:                                                               | Threshold value of the case                                                      |                                                                                  |
| `thresholdType`                                                                  | [models.ThresholdType](../models/thresholdtype.md)                               | :heavy_minus_sign:                                                               | Threshold type indicating if thresholdValue is default or custom.                |                                                                                  |
| `thresholdValueFromCluster`                                                      | *number*                                                                         | :heavy_minus_sign:                                                               | Threshold value of the cluster in which case is created                          |                                                                                  |
| `caseType`                                                                       | [models.CaseType](../models/casetype.md)                                         | :heavy_minus_sign:                                                               | Type of the case. Control or Content type                                        |                                                                                  |
| `questionDetail`                                                                 | [models.CaseQuestionDetail](../models/casequestiondetail.md)[]                   | :heavy_minus_sign:                                                               | Questions in the case                                                            |                                                                                  |
| `link`                                                                           | [models.Link](../models/link.md)                                                 | :heavy_minus_sign:                                                               | Defines the relationship between this resource and another object.               |                                                                                  |