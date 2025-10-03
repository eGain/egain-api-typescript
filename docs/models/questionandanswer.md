# QuestionAndAnswer

Questions and answers of the Casebase

## Example Usage

```typescript
import { QuestionAndAnswer } from "@egain/egain-api-typescript/models";

let value: QuestionAndAnswer = {
  id: "1000003852",
  answers: [
    {
      id: "1000000004",
    },
  ],
};
```

## Fields

| Field                                  | Type                                   | Required                               | Description                            | Example                                |
| -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| `id`                                   | *string*                               | :heavy_check_mark:                     | ID of question                         | 1000003852                             |
| `answers`                              | [models.Answer](../models/answer.md)[] | :heavy_minus_sign:                     | Answers of question                    |                                        |