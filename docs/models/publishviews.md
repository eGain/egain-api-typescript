# PublishViews

## Example Usage

```typescript
import { PublishViews } from "@egain/egain-api-typescript/models";

let value: PublishViews = {
  publishView: [
    {
      id: "PROD-12446",
      tagCategories: [
        {
          tagCategory: [
            {
              tags: {
                tag: [
                  {
                    name: "Blue",
                    id: "PROD-13206",
                  },
                ],
              },
              tagGroups: {
                tagGroup: [
                  {
                    id: "PROD-14566",
                  },
                ],
              },
            },
          ],
        },
      ],
    },
  ],
};
```

## Fields

| Field                                                                                                                                                                                                               | Type                                                                                                                                                                                                                | Required                                                                                                                                                                                                            | Description                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `publishView`                                                                                                                                                                                                       | [models.PublishView](../models/publishview.md)[]                                                                                                                                                                    | :heavy_minus_sign:                                                                                                                                                                                                  | Publish views allow authors to tailor the contents of an article to different audiences by controlling visibility of certain article content using tags.<br><br>The total number of publish views is limited to 20. |