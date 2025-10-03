# GHSearchRequest

## Example Usage

```typescript
import { GHSearchRequest } from "@egain/egain-api-typescript/models";

let value: GHSearchRequest = {
  casebaseId: "409601000000001",
  questions: [
    {
      id: "1000003852",
      answers: [],
    },
  ],
  ghsArticleId: "100000000001035",
};
```

## Fields

| Field                                                                                                 | Type                                                                                                  | Required                                                                                              | Description                                                                                           | Example                                                                                               |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `casebaseId`                                                                                          | *string*                                                                                              | :heavy_check_mark:                                                                                    | The numerical ID of the Casebase.                                                                     | 409601000000001                                                                                       |
| `questions`                                                                                           | [models.StartQuestionAndAnswer](../models/startquestionandanswer.md)[]                                | :heavy_minus_sign:                                                                                    | Pre-answered Questions in Guided Help search                                                          |                                                                                                       |
| `profileId`                                                                                           | *string*                                                                                              | :heavy_minus_sign:                                                                                    | The ID of the guided help profile.<br><br/>1 will always be the **system profile**.<br/>              |                                                                                                       |
| `sessionVariable`                                                                                     | [models.SessionContextVariable](../models/sessioncontextvariable.md)[]                                | :heavy_minus_sign:                                                                                    | Session variables used to give Guided Help additional context.                                        |                                                                                                       |
| `startOver`                                                                                           | *boolean*                                                                                             | :heavy_minus_sign:                                                                                    | Restart the current Guided Help search with the existing context along with session variable context. |                                                                                                       |
| `useLiveRelease`                                                                                      | *boolean*                                                                                             | :heavy_minus_sign:                                                                                    | Use current live release snapshot of the Casebase otherwise use the authoring release.                |                                                                                                       |
| `ghsArticleId`                                                                                        | *string*                                                                                              | :heavy_minus_sign:                                                                                    | Numeric ID of the guided help session article used for starting search.                               | 100000000001035                                                                                       |