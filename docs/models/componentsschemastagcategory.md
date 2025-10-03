# ComponentsSchemasTagCategory

Tag Categories for Interest configured for a portal.

## Example Usage

```typescript
import { ComponentsSchemasTagCategory } from "@egain/egain-api-typescript/models";

let value: ComponentsSchemasTagCategory = {};
```

## Fields

| Field                                                                                                                    | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `name`                                                                                                                   | *string*                                                                                                                 | :heavy_minus_sign:                                                                                                       | Name of the Tag Category                                                                                                 |
| `id`                                                                                                                     | *string*                                                                                                                 | :heavy_minus_sign:                                                                                                       | The ID of the Tag Category.<br>A Tag Category ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `tag`                                                                                                                    | [models.ComponentsSchemasTag](../models/componentsschemastag.md)[]                                                       | :heavy_minus_sign:                                                                                                       | N/A                                                                                                                      |
| `tagGroup`                                                                                                               | [models.ComponentsSchemasTagGroup](../models/componentsschemastaggroup.md)[]                                             | :heavy_minus_sign:                                                                                                       | N/A                                                                                                                      |