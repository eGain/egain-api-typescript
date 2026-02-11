# SearchReplacement

## Example Usage

```typescript
import { SearchReplacement } from "@egain/egain-api-typescript/models";

let value: SearchReplacement = {
  type: "search",
  name: "<value>",
  portalId: "<id>",
  q: "<value>",
};
```

## Fields

| Field                                                                                                                                                   | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`                                                                                                                                                  | [models.SearchReplacementType](../models/searchreplacementtype.md)                                                                                      | :heavy_check_mark:                                                                                                                                      | Identifies this replacement as a **search result**. At execution, results from a portal search will replace the variable `name` in the prompt template. |
| `name`                                                                                                                                                  | *string*                                                                                                                                                | :heavy_check_mark:                                                                                                                                      | The placeholder variable in the prompt template that will be replaced with search results.                                                              |
| `portalId`                                                                                                                                              | *string*                                                                                                                                                | :heavy_check_mark:                                                                                                                                      | The portal identifier where the search will be performed.                                                                                               |
| `q`                                                                                                                                                     | *string*                                                                                                                                                | :heavy_check_mark:                                                                                                                                      | The search query string to run against the specified portal.                                                                                            |