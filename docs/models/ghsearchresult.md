# GHSearchResult

Success

## Example Usage

```typescript
import { GHSearchResult } from "@egain/egain-api-typescript/models";

let value: GHSearchResult = {
  casebase: {
    casebaseId: "409601000000001",
  },
  actionSearch: [
    {
      articleId: "PROD-9312",
      caseId: "100000000001035",
      actionId: "100000000009312",
      articleType: {
        articleTypeId: "932100000002020",
      },
    },
  ],
  answeredQuestion: [
    {
      id: "1000001035",
      validAnswer: [
        {
          id: "1000001035",
        },
      ],
      previousAnswer: [
        {
          id: "1000001035",
        },
      ],
      validAnswerRange: {
        id: "1000001035",
      },
    },
  ],
  caseSearch: [
    {
      action: [
        {
          articleType: {
            articleTypeId: "932100000002020",
          },
        },
      ],
    },
  ],
  dynamicSearch: [
    {
      parentClusterId: "1000001035",
      virtualCase: [
        {
          detailField: [
            {
              id: "PROD-9312",
            },
          ],
          displayField: [
            {
              id: "PROD-9312",
            },
          ],
          dynamicClusterId: "1000001035",
        },
      ],
    },
  ],
  unansweredQuestion: [
    {
      id: "1000001035",
      validAnswer: [
        {
          id: "1000001035",
        },
      ],
      validAnswerRange: {
        id: "1000001035",
      },
    },
  ],
  startupQuestion: [
    {
      id: "1000001035",
      validAnswer: [
        {
          id: "1000001035",
        },
      ],
      validAnswerRange: {
        id: "1000001035",
      },
    },
  ],
  targetClusters: [
    {
      id: "1000000257",
    },
  ],
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `casebase`                                                 | [models.Casebase](../models/casebase.md)                   | :heavy_minus_sign:                                         | N/A                                                        |
| `actionSearch`                                             | [models.ActionSearch](../models/actionsearch.md)[]         | :heavy_minus_sign:                                         | actions in the search                                      |
| `answeredQuestion`                                         | [models.AnsweredQuestion](../models/answeredquestion.md)[] | :heavy_minus_sign:                                         | questions answered in the search                           |
| `caseSearch`                                               | [models.CaseSearch](../models/casesearch.md)[]             | :heavy_minus_sign:                                         | cases in the search                                        |
| `dynamicSearch`                                            | [models.DynamicSearch](../models/dynamicsearch.md)[]       | :heavy_minus_sign:                                         | dynamic cases in the search                                |
| `unansweredQuestion`                                       | [models.Question](../models/question.md)[]                 | :heavy_minus_sign:                                         | unanswered questions in the search                         |
| `startupQuestion`                                          | [models.Question](../models/question.md)[]                 | :heavy_minus_sign:                                         | startup questions in the search                            |
| `targetClusters`                                           | [models.ClusterId](../models/clusterid.md)[]               | :heavy_minus_sign:                                         | active clusters in the search                              |