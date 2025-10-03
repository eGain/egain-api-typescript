# RetrieveResponseAnswer

If a certified answer is given. The answer object will be present. <br><br> This will be shown only if certified answers are configured and the certified answer meets the configured threshold.

## Example Usage

```typescript
import { RetrieveResponseAnswer } from "@egain/egain-api-typescript/models";

let value: RetrieveResponseAnswer = {
  answerValue: "Per the Lending FAQ document...",
  references: [],
  answerType: "certified",
  relevanceScore: 0.99,
};
```

## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  | Example                                                                      |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `answerValue`                                                                | *string*                                                                     | :heavy_check_mark:                                                           | The certified answer.                                                        | Per the Lending FAQ document...                                              |
| `references`                                                                 | [models.ReferenceResponse](../models/referenceresponse.md)[]                 | :heavy_check_mark:                                                           | Source used to produce the certified answer.                                 |                                                                              |
| `answerType`                                                                 | [models.RetrieveResponseAnswerType](../models/retrieveresponseanswertype.md) | :heavy_check_mark:                                                           | Specifies that the answer produced was a certified answer.                   | certified                                                                    |
| `relevanceScore`                                                             | *number*                                                                     | :heavy_check_mark:                                                           | Confidence score (0.0-1.0) reflecting how well the answer matches the query. | 0.99                                                                         |