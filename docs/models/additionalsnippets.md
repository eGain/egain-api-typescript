# AdditionalSnippets

## Example Usage

```typescript
import { AdditionalSnippets } from "@egain/egain-api-typescript/models";

let value: AdditionalSnippets = {
  id: "<id>",
  name: "<value>",
  docType: "Doc",
  docName: "<value>",
  snippet: "<value>",
  relevanceScore: 4844.91,
};
```

## Fields

| Field                                                                                                                 | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                  | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The ID of the Article. <br><br> An Article ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `name`                                                                                                                | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The name of the Article or source content.                                                                            |
| `docType`                                                                                                             | [models.AdditionalSnippetsDocType](../models/additionalsnippetsdoctype.md)                                            | :heavy_check_mark:                                                                                                    | Format of the source document (HTML, Doc, or PDF).                                                                    |
| `docName`                                                                                                             | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | Name of the attachment, if an attachment was used as the source content.                                              |
| `snippet`                                                                                                             | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | A snippet of the article content.                                                                                     |
| `keywordSnippet`                                                                                                      | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | A keyword snippet of the article content.                                                                             |
| `relevanceScore`                                                                                                      | *number*                                                                                                              | :heavy_check_mark:                                                                                                    | Generated confidence score (0.0-1.0) for the snippet's relevance to the query.                                        |