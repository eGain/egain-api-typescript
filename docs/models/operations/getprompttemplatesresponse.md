# GetPromptTemplatesResponse

Successful response with list of prompt templates

## Example Usage

```typescript
import { GetPromptTemplatesResponse } from "@egain/egain-api-typescript/models/operations";

let value: GetPromptTemplatesResponse = {
  promptTemplates: [
    {
      name: "Generate Title",
      id: "PROD-26471",
      description: "Generate article title based on article content",
      active: true,
      useFor: "advisor",
      appliesTo: "article",
      instruction: "I want you to generate...",
      outputFormat: "html",
      createdOn: new Date("2024-04-01T08:00:00Z"),
      modifiedDate: new Date("2024-04-30T17:30:00Z"),
      createdBy: {},
      reviewStatus: "published",
      isSystemCreated: false,
      fieldToUpdate: "custom.contactPerson.cust1",
    },
  ],
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `promptTemplates`                                         | [models.PromptTemplate](../../models/prompttemplate.md)[] | :heavy_minus_sign:                                        | N/A                                                       |