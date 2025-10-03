# Question

## Example Usage

```typescript
import { Question } from "@egain/egain-api-typescript/models";

let value: Question = {
  id: "1000001035",
  validAnswer: [
    {
      id: "1000001035",
    },
  ],
  validAnswerRange: {
    id: "1000001035",
  },
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            | Example                                                                |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `id`                                                                   | *string*                                                               | :heavy_minus_sign:                                                     | The numerical ID of the question                                       | 1000001035                                                             |
| `title`                                                                | *string*                                                               | :heavy_minus_sign:                                                     | Title of the question                                                  |                                                                        |
| `type`                                                                 | [models.QuestionType](../models/questiontype.md)                       | :heavy_minus_sign:                                                     | type of the question                                                   |                                                                        |
| `format`                                                               | [models.QuestionFormat](../models/questionformat.md)                   | :heavy_minus_sign:                                                     | format of the question                                                 |                                                                        |
| `shortName`                                                            | *string*                                                               | :heavy_minus_sign:                                                     | short name                                                             |                                                                        |
| `hasAdditionalInfo`                                                    | *boolean*                                                              | :heavy_minus_sign:                                                     | indicates if question has additional information                       |                                                                        |
| `hasAction`                                                            | *boolean*                                                              | :heavy_minus_sign:                                                     | indicates if question has action                                       |                                                                        |
| `validAnswer`                                                          | [models.SchemasAnswer](../models/schemasanswer.md)[]                   | :heavy_minus_sign:                                                     | valid answers for question                                             |                                                                        |
| `validAnswerRange`                                                     | [models.AnswerRange](../models/answerrange.md)                         | :heavy_minus_sign:                                                     | N/A                                                                    |                                                                        |
| `metadata`                                                             | [models.Metadata](../models/metadata.md)[]                             | :heavy_minus_sign:                                                     | Metadata on question                                                   |                                                                        |
| `customAttributes`                                                     | [models.SchemasCustomAttribute](../models/schemascustomattribute.md)[] | :heavy_minus_sign:                                                     | Custom attributes of question                                          |                                                                        |