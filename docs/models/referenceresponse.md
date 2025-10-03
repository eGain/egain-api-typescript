# ReferenceResponse

One document used in generated response

## Example Usage

```typescript
import { ReferenceResponse } from "@egain/egain-api-typescript/models";

let value: ReferenceResponse = {
  id: "<id>",
  name: "<value>",
  docType: "Doc",
  source: "eGain Article",
};
```

## Fields

| Field                                                                                                                 | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                  | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The ID of the Article. <br><br> An Article ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `name`                                                                                                                | *string*                                                                                                              | :heavy_check_mark:                                                                                                    | The name of the Article or source content.                                                                            |
| `docName`                                                                                                             | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | Name of the attachment, if an attachment was used as the source content.                                              |
| `docType`                                                                                                             | [models.ReferenceResponseDocType](../models/referenceresponsedoctype.md)                                              | :heavy_check_mark:                                                                                                    | Format of the source document (HTML, Doc, or PDF).                                                                    |
| `source`                                                                                                              | [models.ReferenceResponseSource](../models/referenceresponsesource.md)                                                | :heavy_check_mark:                                                                                                    | Source Type                                                                                                           |
| `link`                                                                                                                | [models.ReferenceResponseLink](../models/referenceresponselink.md)                                                    | :heavy_minus_sign:                                                                                                    | Defines the relationship between this resource and another object.                                                    |