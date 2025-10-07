# Components

**Comonents**: 

Health status of import service componenets


## Example Usage

```typescript
import { Components } from "@egain/egain-api-typescript/models/operations";

let value: Components = {};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `database`                                                                 | [operations.Database](../../models/operations/database.md)                 | :heavy_minus_sign:                                                         | Health status of database component.                                       |
| `fileSystem`                                                               | [operations.FileSystem](../../models/operations/filesystem.md)             | :heavy_minus_sign:                                                         | Health status of file system component.                                    |
| `externalServices`                                                         | [operations.ExternalServices](../../models/operations/externalservices.md) | :heavy_minus_sign:                                                         | Health status of external services components.                             |
| `processingEngine`                                                         | [operations.ProcessingEngine](../../models/operations/processingengine.md) | :heavy_minus_sign:                                                         | Health status of processing engine component.                              |
| `storage`                                                                  | [operations.Storage](../../models/operations/storage.md)                   | :heavy_minus_sign:                                                         | Health status of storage component.                                        |