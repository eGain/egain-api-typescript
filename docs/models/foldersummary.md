# FolderSummary

This schema contains the topic ID and name of the Folder. This is used by FolderBreadcrumb.

## Example Usage

```typescript
import { FolderSummary } from "@egain/egain-api-typescript/models";

let value: FolderSummary = {};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `id`                                           | *number*                                       | :heavy_minus_sign:                             | ID of the folder.                              |
| `name`                                         | *string*                                       | :heavy_minus_sign:                             | Name of the folder.                            |
| `link`                                         | [models.SchemasLink](../models/schemaslink.md) | :heavy_minus_sign:                             | N/A                                            |