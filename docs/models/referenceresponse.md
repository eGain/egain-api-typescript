# ReferenceResponse

One document used in generated response

## Example Usage

```typescript
import { ReferenceResponse } from "@egain/egain-api-typescript/models";

let value: ReferenceResponse = {
  id: "PROD-7297",
  name: "Fair Lending FAQs",
  docName: "Lending FAQs",
  docType: "PDF",
  source: "eGain Attachment",
  topicBreadcrumb: [
    {
      topicSummary: [
        {
          id: "PROD-1921",
          name: "Banking Regulations",
        },
      ],
    },
  ],
};
```

## Fields

| Field                                                                                                                 | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           | Example                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                  | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The ID of the Article. <br><br> An Article ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. | PROD-7297                                                                                                             |
| `name`                                                                                                                | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The name of the Article or source content.                                                                            | Fair Lending FAQs                                                                                                     |
| `docName`                                                                                                             | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | Name of the attachment, if an attachment was used as the source content.                                              | Lending FAQs                                                                                                          |
| `docType`                                                                                                             | [models.ReferenceResponseDocType](../models/referenceresponsedoctype.md)                                              | :heavy_check_mark:                                                                                                    | Format of the source document (HTML, DOCX, PPTX, or PDF).                                                             | PDF                                                                                                                   |
| `source`                                                                                                              | [models.ReferenceResponseSource](../models/referenceresponsesource.md)                                                | :heavy_check_mark:                                                                                                    | Source Type                                                                                                           | eGain Attachment                                                                                                      |
| `topicBreadcrumb`                                                                                                     | [models.AITopicBreadcrumb](../models/aitopicbreadcrumb.md)[]                                                          | :heavy_minus_sign:                                                                                                    | N/A                                                                                                                   |                                                                                                                       |