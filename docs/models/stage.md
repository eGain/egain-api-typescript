# Stage

A stage in the Article's workflow.

## Example Usage

```typescript
import { Stage } from "@egain/egain-api-typescript/models";

let value: Stage = {};
```

## Fields

| Field                                      | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `name`                                     | *string*                                   | :heavy_minus_sign:                         | The name of the stage.                     |
| `milestone`                                | [models.Milestone](../models/milestone.md) | :heavy_minus_sign:                         | A resource's workflow milestone.           |