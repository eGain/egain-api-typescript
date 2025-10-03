# StartGHSearchResponse

## Example Usage

```typescript
import { StartGHSearchResponse } from "@egain/egain-api-typescript/models/operations";

let value: StartGHSearchResponse = {
  headers: {
    "key": [
      "<value 1>",
    ],
  },
  result: {
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
  },
};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `headers`                                               | Record<string, *string*[]>                              | :heavy_check_mark:                                      | N/A                                                     |
| `result`                                                | [models.GHSearchResult](../../models/ghsearchresult.md) | :heavy_check_mark:                                      | N/A                                                     |