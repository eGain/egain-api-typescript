# StartQuestionAndAnswer

Questions and answers of the Casebase

## Example Usage

```typescript
import { StartQuestionAndAnswer } from "@egain/egain-api-typescript/models";

let value: StartQuestionAndAnswer = {
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
| `answers`                              | [models.Answer](../models/answer.md)[] | :heavy_check_mark:                     | Answers of question                    |                                        |