# CaseQuestionDetail

## Example Usage

```typescript
import { CaseQuestionDetail } from "@egain/egain-api-typescript/models";

let value: CaseQuestionDetail = {
  question: {
    id: "1000001035",
  },
  answer: [],
};
```

## Fields

| Field                                            | Type                                             | Required                                         | Description                                      |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `question`                                       | [models.CaseQuestion](../models/casequestion.md) | :heavy_check_mark:                               | N/A                                              |
| `answer`                                         | [models.CaseAnswer](../models/caseanswer.md)[]   | :heavy_check_mark:                               | Answer of the question                           |
| `scoringValue`                                   | *number*                                         | :heavy_minus_sign:                               | Weightage of the question                        |